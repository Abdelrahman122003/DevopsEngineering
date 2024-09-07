## systemd

In the context of systemd in Linux, parallelization capabilities refer to the ability to start multiple services or units simultaneously rather than sequentially. This can significantly speed up the boot process and improve system performance, especially on systems with multiple CPU cores.

### structure of systemd

1. **[Unit]: Metadata and Dependencies**
   The [Unit] section contains general information about the unit and its dependencies. This section is common to all unit types (service, socket, target, etc.).

   Key Directives:

   - Description: A short, human-readable description of the unit.

   - Documentation: Links to documentation for the unit, such as a URL or man page.

   - After: Specifies the order in which units are started. This unit will start after the specified units.

   - Requires: Specifies that this unit requires the specified units to be active for it to start. If the required unit fails to start, this unit will not be started.

   - Wants: Similar to Requires, but less strict. If the specified units fail to start, this unit will still be started.

2. **[Service]: Service-Specific Settings**
   The [Service] section contains settings that are specific to service units. It defines how the service should be started, stopped, and managed.

   Key Directives:

   - ExecStart: The command to start the service.

   - ExecStop: The command to stop the service (optional).

   - ExecReload: The command to reload the service configuration without stopping it (optional).

   - Type: Specifies the startup type of the service. Common values include:

   - simple: The service starts and systemd considers it running as soon as the ExecStart command is executed.

   - forking: The service forks a child process that continues running in the background.

   - oneshot: The service is expected to run a single task and then exit.

   - notify: The service sends a notification message to systemd when it is ready.

   - Restart: Specifies the restart behavior of the service. Common values include always, on-failure, on-abnormal, etc.

3. **[Install]: Installation Settings**
   The [Install] section contains information about how the unit should be installed. This section is primarily used by the systemctl enable and systemctl disable commands.

   Key Directives:

   - WantedBy: Specifies the target units this unit should be enabled for. Common values include multi-user.target and graphical.target.

   - RequiredBy: Similar to WantedBy, but specifies a stronger dependency.

   - Alias: Defines additional names for the unit.

### Managing Services with Systemd

- `Start a service`:

  ```shell
  systemctl start service_name
  ```

- `Stop a service`:

  ```shell
  systemctl stop service_name
  ```

- `Enable a service`:<br>
  Enabling a service in systemd means configuring the service to start automatically when the system boots up or when a specific target is reached. This does not start the service immediately; it just ensures that the service will start on the next boot or when the specified conditions are met.

  ```shell
  systemctl enable service_name
  ```

- `Disable a service`:<br>
  Disabling a service in systemd means configuring the service not to start automatically when the system boots up or when a specific target is reached. This does not stop the service if it is currently running; it just prevents it from starting automatically in the future.
  ```shell
  systemctl disable service_name
  ```
- `Check service status`:

  ```shell
  systemctl status service_name
  ```

- `View logs`:<br>
  The `journalctl -u nameServices` is a powerful way to troubleshoot and monitor specific services on a systemd-based system, giving you detailed insights into their behavior and any issues they may encounter.
