# Registry Settings Keeper

## App Settings

- `LogLevel` - can be any of the following (optional; defaults to `Info`)

  - `Trace` - Verbose debugging. Includes messages to indicate every method entry and exit point,
              as well as other significant points in the flow of the code.
  - `Debug` - Includes app settings and parameter values, and local variable values at key points.
  - `Info` - Information messages about the state of the application or significant events,
             e.g., when a registry setting was externally modified and had to be reset.
  - `Warn` - Messages that indicate an unusual condition that may indicate a problem,
             but did not cause an error.
  - `Error` - An error that caused a certain piece of functionality to break,
              but allowed the application to keep running.
  - `Fatal` - An error that forces the application to exit.

## Troubleshooting

### App exits immediately after starting

If any of the required startup steps fails -- such as initializing the `Log` class --
the application will terminate.

When this happens, the error details will be written to the **Windows Event Viewer**
under *Windows Logs > Application*, as events with the Source "RegistryEnforcer".
