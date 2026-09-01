=====================
Writing Diary Entries
=====================


Writing diary entries is important so that PyWeek remains a social event. It
is intended that entrants learn from and support each other.


Writing Diaries
===============

It is recommended to write at least one diary a day, including a screenshot
of your progress.

This will be interesting to other PyWeek participants, but will also give you
the chance, once the competition has ended, to look back and see how your game
evolved over the course of a week.

Screenshots can be uploaded to the PyWeek website via the “Upload File” link
on the Entry page.


Taking Screenshots
==================

While you can take screenshots using a generic screen grab tool, it’s not
always quick and easy — it can require switching focus away from your game.

You can take more and better screenshots if you set up a key — I suggest F12 —
to save a new screenshot under a unique file name.

Fortunately doing this from Python code is pretty formulaic.


Pygame
------

Pygame can directly save a surface as an image. The code to do this just needs
to be dropped into your event handling.


.. code-block:: python

    import datetime
    import pygame


    def screenshot_path():
        """Get a path to save a screenshot into."""
        now = datetime.datetime.now()
        return now.strftime('screenshot_%Y-%m-%d_%H:%M:%S.%f.png')


    # in your event loop
    for event in pygame.event.get():
        ...

        if event.type == KEYDOWN:
            if event.key == K_F12:
                pygame.image.save(screen_surface, screenshot_path())


Pyglet
------

In OpenGL, you have to read back the colour buffer to an image and save that.
As you generally don’t want the colour buffer’s alpha channel to be saved if it
has one, there are a couple of OpenGL calls to force every pixel to be read as
opaque. Pyglet can handle reading and saving the colour buffer though.


.. code-block:: python

    import datetime

    from pyglet import gl
    from pyglet.window import key

    def screenshot_path():
        """Get a path to save a screenshot into."""
        now = datetime.datetime.now()
        return now.strftime('screenshot_%Y-%m-%d_%H:%M:%S.%f.png')


    ...


    def on_key_press(symbol, modifiers):
        """This is your registered on_key_press handler.

        window is the pyglet.window.Window object to grab; here we
        assume this is a global.
        """
        if symbol == key.F12:
            # disable transfer alpha channel
            gl.glPixelTransferf(gl.GL_ALPHA_BIAS, 1.0)

            image = pyglet.image.ColorBufferImage(
                0, 0,
                window.width, window.height
            )
            image.save(screenshot_path())

            # re-enable alpha channel transfer
            gl.glPixelTransferf(gl.GL_ALPHA_BIAS, 0.0)


ModernGL
--------

For `ModernGL <https://moderngl.readthedocs.io/>`_ the raw OpenGL calls are
wrapped in an object-oriented API. You will need a library to convert the raw
image data to a graphics file format. The buffer data will need to be
vertically flipped.

Here is the code to do that using Pygame:


.. code-block:: python

    import datetime
    import pygame.image
    import pygame.transform


    def screenshot(ctx: moderngl.Context):
        """Take a screenshot."""
        now = datetime.datetime.now()
        filename = f'screenshot_{now:%Y-%m-%d_%H:%M:%S.%f}.png'

        # You can use this code to take a screenshot of any FBO but
        # the default framebuffer, ie. the screen, is ctx.screen.
        fbo = ctx.screen

        # Read RGB data back from the screen
        data = fbo.read(components=3)

        # Make an RGB Pygame Surface
        surf = pygame.image.fromstring(
            data,
            (fbo.width, fbo.height),
            'RGB'
        )

        # Vertically flip the image
        surf = pygame.transform.flip(surf, False, True)

        # Save Pygame surface to a file
        pygame.image.save(surf, filename)


And instead using Pillow:


.. code-block:: python

    import datetime
    from PIL import Image


    def screenshot(ctx: moderngl.Context):
        """Take a screenshot."""
        now = datetime.datetime.now()
        filename = f'screenshot_{now:%Y-%m-%d_%H:%M:%S.%f}.png'

        # You can use this code to take a screenshot of any FBO but
        # the default framebuffer, ie. the screen, is ctx.screen.
        fbo = ctx.screen

        # Read RGB data back from the screen
        data = fbo.read(components=3)

        # Make an RGB PIL image
        img = Image.frombytes(
            'RGB',
            (fbo.width, fbo.height),
            data,
        )

        # Vertically flip the image
        image = image.transpose(Image.FLIP_TOP_BOTTOM)

        # Save Image to a file
        img.save(filename, format='png')

