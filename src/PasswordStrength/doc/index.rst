Symfony UX Password Strength
============================

Symfony UX Password Strength is a Symfony bundle integrating a password strength estimator
in Symfony applications. It is part of `the Symfony UX initiative`_.

The password strength estimation method is the same as the default Symfony Constraint `PasswordStrength`.

.. image:: Animation.gif
  :alt: Strength computed when typing

Installation
------------

Before you start, make sure you have `Symfony UX configured in your app`_.

Then install the bundle using Composer and Symfony Flex:

.. code-block:: terminal

    $ composer require symfony/ux-password-strength

    # Don't forget to install the JavaScript dependencies as well and compile
    $ npm install --force
    $ npm run watch

    # or use yarn
    $ yarn install --force
    $ yarn watch

Also make sure you have at least version 3.2.1 of
`@symfony/stimulus-bridge`_ in your ``package.json`` file.

Usage
-----

.. code-block:: html+twig

    <form {{ stimulus_controller('@symfony/ux-password-strength') }}>
        <label for="password">Password</label>
        <input id="password" name="password" type="password" {{ stimulus_action('@symfony/ux-password-strength', 'estimatePasswordStrength') }}>
        <div>The score is: <span {{ stimulus_target('@symfony/ux-password-strength', 'score') }}></span></div>
        <div>The message is: <span {{ stimulus_target('@symfony/ux-password-strength', 'message') }}></span></div>
    </form>


That's it! Password Strength now shows the estimated password strength
when typing a password.
You can customize the way it is rendered.

.. note::

Backward Compatibility promise
------------------------------

This bundle aims at following the same Backward Compatibility promise as
the Symfony framework:
https://symfony.com/doc/current/contributing/code/bc.html

.. _`the Symfony UX initiative`: https://symfony.com/ux
.. _`@symfony/stimulus-bridge`: https://github.com/symfony/stimulus-bridge
.. _`Symfony UX configured in your app`: https://symfony.com/doc/current/frontend/ux.html
