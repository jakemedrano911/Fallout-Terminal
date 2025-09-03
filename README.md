# Terminal Configuration

This project renders a retro terminal interface that reads its content from
`config.json`. You can supply your own configuration file at runtime through the
page itself.

## Loading a custom configuration

1. Open `index.html` in your browser.
2. Use the **Config** file input beside the power button to select a JSON file
   that matches the structure of `config.json`.
3. Press the **Power** button to start the terminal. The uploaded configuration
   will be used if provided; otherwise the default `config.json` is loaded.

If you power off the terminal you can choose a different file and power on
again to reload with the new configuration.


## Optional Passwords and Dud Words

The hacking mini-game can be customized by providing a `password` and optional
`dudWords` in the `hacking` section of the configuration. This allows you to
control exactly which words appear during the puzzle.

- If you supply more candidate words than the selected difficulty requires, only
  your words are used.
- If you only provide `dudWords` and omit `password`, one of the provided
  words is selected as the password and the rest remain duds. Any additional
  slots are backfilled with random entries from the internal list if needed.
- If you supply fewer words, the remaining slots are backfilled with random
  entries from the internal list.
- The length of the provided password sets the length of all candidate words,
  overriding the difficulty's normal character-length range.

Example:

```json
{
  "hacking": {
    "difficulty": "Average",
    "password": "HARDWARE",
    "dudWords": ["RESEARCH", "SCIENTIST"]
  }
}
```

In this example the password is eight letters long, so every generated word will
also contain eight characters. Because only two dud words are supplied, the
terminal backfills the remaining required words with random eight-letter
candidates.
