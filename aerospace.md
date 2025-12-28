# Aerospace settings

`cursor ~/.aerospace.toml`

```toml
config-version = 2

# You can use it to add commands that run after AeroSpace startup.
# Available commands : https://nikitabobko.github.io/AeroSpace/commands
after-startup-command = []

exec-on-workspace-change = []

# Start AeroSpace at login
start-at-login = true

# Normalizations. See: https://nikitabobko.github.io/AeroSpace/guide#normalization
enable-normalization-flatten-containers = true
enable-normalization-opposite-orientation-for-nested-containers = true

accordion-padding = 20

# Possible values: tiles|accordion
default-root-container-layout = 'accordion'

# Possible values: horizontal|vertical|auto
# 'auto' means: wide monitor (anything wider than high) gets horizontal orientation,
#               tall monitor (anything higher than wide) gets vertical orientation
default-root-container-orientation = 'auto'

# Mouse follows focus when focused monitor changes
# Drop it from your config, if you don't like this behavior
# See https://nikitabobko.github.io/AeroSpace/guide#on-focus-changed-callbacks
# See https://nikitabobko.github.io/AeroSpace/commands#move-mouse
# Fallback value (if you omit the key): on-focused-monitor-changed = []
on-focused-monitor-changed = ['move-mouse monitor-lazy-center']

# You can effectively turn off macOS "Hide application" (cmd-h) feature by toggling this flag
# Useful if you don't use this macOS feature, but accidentally hit cmd-h or cmd-alt-h key
# Also see: https://nikitabobko.github.io/AeroSpace/goodies#disable-hide-app
automatically-unhide-macos-hidden-apps = true

on-mode-changed = []

[key-mapping]
    preset = 'qwerty'

[gaps]
    inner.horizontal = 10
    inner.vertical =   10
    outer.left =       10
    outer.bottom =     10
    outer.top =        10
    outer.right =      10

[mode.main.binding]

    # All possible keys:
    # - Letters.        a, b, c, ..., z
    # - Numbers.        0, 1, 2, ..., 9
    # - Keypad numbers. keypad0, keypad1, keypad2, ..., keypad9
    # - F-keys.         f1, f2, ..., f20
    # - Special keys.   minus, equal, period, comma, slash, backslash, quote, semicolon,
    #                   backtick, leftSquareBracket, rightSquareBracket, space, enter, esc,
    #                   backspace, tab, pageUp, pageDown, home, end, forwardDelete,
    #                   sectionSign (ISO keyboards only, european keyboards only)
    # - Keypad special. keypadClear, keypadDecimalMark, keypadDivide, keypadEnter, keypadEqual,
    #                   keypadMinus, keypadMultiply, keypadPlus
    # - Arrows.         left, down, up, right

    # All possible modifiers: cmd, alt, ctrl, shift

    # All possible commands: https://nikitabobko.github.io/AeroSpace/commands

    # See: https://nikitabobko.github.io/AeroSpace/commands#exec-and-forget
    # You can uncomment the following lines to open up terminal with alt + enter shortcut
    # (like in i3)
    # alt-enter = '''exec-and-forget osascript -e '
    # tell application "Terminal"
    #     do script
    #     activate
    # end tell'
    # '''

    # See: https://nikitabobko.github.io/AeroSpace/commands#layout
    alt-n = 'layout accordion horizontal vertical'
    alt-m = 'layout tiles horizontal vertical'

    # See: https://nikitabobko.github.io/AeroSpace/commands#focus
    alt-q = 'focus left'
    alt-s = 'focus down'
    alt-w = 'focus up'
    alt-e = 'focus right'

    alt-u = 'focus left'
    alt-k = 'focus down'
    alt-i = 'focus up'
    alt-o = 'focus right'

    # See: https://nikitabobko.github.io/AeroSpace/commands#move
    alt-shift-q = 'move left'
    alt-shift-s = 'move down'
    alt-shift-w = 'move up'
    alt-shift-e = 'move right'

    alt-shift-u = 'move left'
    alt-shift-k = 'move down'
    alt-shift-i = 'move up'
    alt-shift-o = 'move right'

    # See: https://nikitabobko.github.io/AeroSpace/commands#resize
    alt-minus = 'resize smart -50'
    alt-equal = 'resize smart +50'

    # See: https://nikitabobko.github.io/AeroSpace/commands#workspace
    alt-1 = 'workspace 1'
    alt-2 = 'workspace 2'
    alt-3 = 'workspace 3'
    alt-4 = 'workspace 4'
    alt-5 = 'workspace 5'
    alt-6 = 'workspace 6'
    alt-7 = 'workspace 7'
    alt-8 = 'workspace 8'
    alt-9 = 'workspace 9'

    # See: https://nikitabobko.github.io/AeroSpace/commands#move-node-to-workspace
    alt-shift-1 = 'move-node-to-workspace 1'
    alt-shift-2 = 'move-node-to-workspace 2'
    alt-shift-3 = 'move-node-to-workspace 3'
    alt-shift-4 = 'move-node-to-workspace 4'
    alt-shift-5 = 'move-node-to-workspace 5'
    alt-shift-6 = 'move-node-to-workspace 6'
    alt-shift-7 = 'move-node-to-workspace 7'
    alt-shift-8 = 'move-node-to-workspace 8'
    alt-shift-9 = 'move-node-to-workspace 9'

    # See: https://nikitabobko.github.io/AeroSpace/commands#workspace-back-and-forth
    alt-tab = 'workspace-back-and-forth'

    alt-a = 'workspace prev --wrap-around'
    alt-d = 'workspace next --wrap-around'
    alt-j = 'workspace prev --wrap-around'
    alt-l = 'workspace next --wrap-around'
    alt-b = 'exec-and-forget open -a /Applications/Brave\ Browser.app'
    alt-x = 'exec-and-forget open -a /Applications/Brave\ Browser.app'
    alt-c = 'exec-and-forget open -a /Applications/Cursor.app'
    alt-f = 'exec-and-forget open -a /Applications/Figma.app'
    alt-g = 'exec-and-forget open -a /Applications/Ghostty.app'
    alt-t = 'exec-and-forget open -a /Applications/Ghostty.app'

```
