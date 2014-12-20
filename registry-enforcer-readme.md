# Registry Enforcer

## App Settings

- `LogLevel` - (optional; defaults to `Info`) Can be any of the values below.
               Note that each of these levels is inclusive of the levels below it;
               e.g., `Error` also includes all messages that would be logged
               with a log level of `Fatal`.

  - `Trace` - Verbose debugging; logs messages to indicate every method entry and exit point,
              local variable values at key points, and other significant points in the flow of the code.
  - `Debug` - Logs app settings at startup, and parameter values at every method call.
  - `Info` - Logs informational messages about the state of the application or significant events,
             e.g., when a registry setting was externally modified and had to be reset.
  - `Warn` - Logs unusual condition that may indicate a problem, but are not causing errors.
  - `Error` - Logs non-fatal errors, i.e., errors that cause a certain piece of functionality to break,
              but allow the application to keep running.
  - `Fatal` - Only logs details about errors that force the application to exit.

## Troubleshooting

### App exits immediately after starting

If any of the required startup steps fails -- such as initializing the `Log` class --
the application will terminate.

When this happens, the error details will be written to the Windows Event Log.
These details can be viewed by opening the **Windows Event Viewer**
(*Start > Control Panel > Administrative Tools > Event Viewer*),
navigating to *Windows Logs > Application*, and filtering for events with a Source of "RegistryEnforcer".
