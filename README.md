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

