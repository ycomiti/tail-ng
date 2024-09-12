# tail-ng

**tail-ng** is a simple Bash script designed to reverse log viewing with real-time updates, combining the power of `tac`, `head`, and `watch`.

## Installation

To install the `tail-ng` script on your system, use the following `curl` command.<br>
This command downloads the script from the GitHub repository and installs it to `/usr/bin` with the appropriate permissions.

Run the following command as a superuser (root):

```bash
sudo bash -c 'file="/usr/bin/tail-ng"; curl -L "https://raw.githubusercontent.com/ycomiti/tail-ng/main/tail-ng" --output "${file}"; chown -v root:root "${file}"; chmod -v 755 "${file}"'
```

### Command Details

- `curl -L "https://raw.githubusercontent.com/ycomiti/tail-ng/main/tail-ng" --output "${file}"`: Downloads the `tail-ng` script from the GitHub repository.
- `chown -v root:root "${file}"`: Changes the owner of the script to `root`.
- `chmod -v 755 "${file}"`: Sets the script permissions to be executable by everyone.

## Usage

After installation, you can use the `tail-ng` script to monitor logs in reverse order with real-time updates.<br>
Here’s how to use it:

### Basic Syntax

```bash
tail-ng <file> [numberOfLines] [refreshRate]
```

- `<file>`: The path to the log file you want to monitor.
- `[numberOfLines]` (optional): The number of lines to display (default: 10).
- `[refreshRate]` (optional): The refresh rate in seconds (default: 0.6).

### Examples

- Monitor the last 10 lines of `access.log` with the default refresh rate (0.6 seconds):

    ```bash
    tail-ng /var/log/apache2/access.log
    ```

- Monitor the last 20 lines of `access.log` and refresh every 1 second:

    ```bash
    tail-ng /var/log/apache2/access.log 20 1
    ```

- Monitor the last 5 lines of `syslog` and refresh every 0.2 seconds:

    ```bash
    tail-ng /var/log/syslog 5 0.2
    ```

### Notes

- Ensure that the log file you want to monitor exists and is readable before running the command.<br>
  If the file does not exist or isn't readable, the script will display an error message.
- The script validates the number of lines and refresh rate to make sure they are valid positive numbers.

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.<br>
You may copy, modify, and redistribute this software under the terms of this license.<br>
For more information, please refer to the `LICENSE` file included in this repository.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.<br>
For more details, see the `CONTRIBUTING.md` file.

## Support

For support or issues, please open an issue on the [GitHub repository](https://github.com/ycomiti/tail-ng/issues).
