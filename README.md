# Auto Zoom Joiner

Automate recurring Zoom meetings with a lightweight Python helper. Auto Zoom Joiner opens the meeting link for you at the time you define and sends a desktop notification confirming the action, so you never have to worry about missing a session.

## Features
- 📅 **Recurring schedules:** Configure different Zoom links for the days and times you need.
- 🔔 **Desktop notifications:** Receive confirmation every time a meeting link is launched.
- 🪟 **Simple setup:** Only a handful of dependencies and a small Python script.

## Requirements
- Python 3.9 or later
- Windows notifications are supported via [plyer](https://plyer.readthedocs.io/) (other platforms may work, but have not been tested)

## Installation
1. **Clone the repository**
   ```bash
   git clone https://github.com/MaxieDev/Auto-Zoom-Joiner.git
   cd Auto-Zoom-Joiner
   ```
2. **Install dependencies**
   ```bash
   pip install plyer schedule
   ```

## Configuration
1. Open `main.py` in your editor of choice.
2. Replace the placeholder URLs in `self.zoom_class_1`, `self.zoom_class_2`, and `self.zoom_class_3` with your meeting links.
3. Update the `schedule.every().<day>.at("HH:MM:SS")` entries inside `schedule_classes()` to match your timetable. The script uses 24-hour time.

```python
    schedule.every().tuesday.at("13:02:00").do(self.join_class, self.zoom_class_1)
```

Add or remove schedule lines as needed—each line calls `join_class` with the appropriate meeting link.

## Usage
Run the script once your configuration is saved:

```bash
python main.py
```

Leave the script running; it will poll every second and automatically open Zoom links at the scheduled times while displaying notifications.

## Troubleshooting
- **Nothing happens at the scheduled time:** Ensure your computer clock is correct and the script remains running.
- **Notifications do not appear:** Confirm that system notifications are enabled and supported on your platform.
- **Schedule changes:** Edit `main.py` and restart the script to load the new times and links.

## License
Distributed under the GPL-3.0 License. See [`LICENSE`](LICENSE) for full details.

## Support
Need help or want to share improvements? Join the community on [Discord](https://discord.gg/rySbUJS64t).
