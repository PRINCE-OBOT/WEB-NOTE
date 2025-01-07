font-size must never be in px. This is a big accessibility issue, as it prevents the font size from scaling with the user's default setting in the browser. Use rem instead.

By default the browser uses 16px for rem, so if the user changes his browser default font-size `rem` adjust accordingly to scale with the user default settings.