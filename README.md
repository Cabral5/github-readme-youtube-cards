# GitHub Readme YouTube Cards

Workflow for displaying recent YouTube videos as SVG cards in your readme

## Usage

Create a file in your `.github/workflows` and give it a name such as `youtube-cards.yml` with the following contents:

```yml
name: GitHub Readme YouTube Cards
on:
    schedule:
        # Runs every hour, on the hour
        - cron: "0 * * * *"
    workflow_dispatch:

jobs:
    deploy:
        runs-on: ubuntu-latest
        steps:
            - uses: DenverCoder1/github-readme-youtube-cards@main
              with:
                  channel_id: UCipSxT7a3rn81vGLw9lqRkg
```

Make sure to change the channel_id to your YouTube channel ID. See below for advanced configuration.

## Live Example

<!-- BEGIN YOUTUBE-CARDS -->
![Automatically Deploy to Fly.io from GitHub with Actions](https://youtube-cards.onrender.com/?id=6u9BrDaSHJc&title=Automatically+Deploy+to+Fly.io+from+GitHub+with+Actions&timestamp=1661864404&views=155 "Automatically Deploy to Fly.io from GitHub with Actions") ![Hosting a Python Discord Bot for Free with Fly.io](https://youtube-cards.onrender.com/?id=J7Fm7MdZn_E&title=Hosting+a+Python+Discord+Bot+for+Free+with+Fly.io&timestamp=1661708747&views=475 "Hosting a Python Discord Bot for Free with Fly.io") ![Making a Wordle Clone Discord Bot with Python (Nextcord)](https://youtube-cards.onrender.com/?id=0p_eQGKFY3I&title=Making+a+Wordle+Clone+Discord+Bot+with+Python+%28Nextcord%29&timestamp=1643900217&views=4086 "Making a Wordle Clone Discord Bot with Python (Nextcord)") ![Run Open Source Code in Seconds with GitPod](https://youtube-cards.onrender.com/?id=Mt_Bsj6K9Lw&title=Run+Open+Source+Code+in+Seconds+with+GitPod&timestamp=1642108413&views=3743 "Run Open Source Code in Seconds with GitPod") ![Custom Help Commands [#2] Select Menus - Python Discord Bot](https://youtube-cards.onrender.com/?id=xsA5QAkr-04&title=Custom+Help+Commands+%5B%232%5D+Select+Menus+-+Python+Discord+Bot&timestamp=1633051808&views=10083 "Custom Help Commands [#2] Select Menus - Python Discord Bot") ![Custom Help Commands [#1] Embeds - Python Discord Bot](https://youtube-cards.onrender.com/?id=TzR8At0SFQI&title=Custom+Help+Commands+%5B%231%5D+Embeds+-+Python+Discord+Bot&timestamp=1632947582&views=8491 "Custom Help Commands [#1] Embeds - Python Discord Bot")
<!-- END YOUTUBE-CARDS -->

## Advanced Configuration

See [action.yml](https://github.com/DenverCoder1/github-readme-youtube-cards/blob/main/action.yml).

| Option             | Description                                      | Default                                                 |
| ------------------ | ------------------------------------------------ | ------------------------------------------------------- |
| `channel_id`       | The channel ID to use for the feed               | Required                                                |
| `comment_tag_name` | The name of the comment tag to use for the cards | "YOUTUBE-CARDS"                                         |
| `max_videos`       | The maximum number of videos to display          | 6                                                       |
| `base_url`         | The base URL to use for the cards                | "https://youtube-cards.onrender.com/"                   |
| `committer_name`   | The name of the committer                        | "GitHub Actions"                                        |
| `committer_email`  | The email address of the committer               | "41898282+github-actions[bot]@users.noreply.github.com" |

## Contributing

Installing dependencies:

```bash
# Dependencies for running the Flask server
poetry install

# Dependencies for testing and development
poetry install --with dev

# Dependencies for running the action script
pip install feedparser
```

Running the Flask server

```bash
gunicorn web.app:app
```

Running the action Python script locally

```bash
python action.py --channel_id=UCipSxT7a3rn81vGLw9lqRkg
```

Running tests

```bash
tox
```
