# 🚀 New and Improved Version Available!

This project has been upgraded to a more advanced and flexible version: **[Chess.com Stats SVG Generator](https://github.com/Prathamesh-B/chesscom-stats-svg)**. The new project offers:

- **Dynamic SVG Generation**: Creates visually appealing SVG images with real-time Chess.com stats.
- **Customizable Themes**: Choose from multiple themes (e.g., default, dark, light) to match your style.
- **Easy Deployment**: Deploy on Vercel with a single click for personalized use.

Check out the [new project](https://github.com/Prathamesh-B/chesscom-stats-svg) and try it out by adding `https://chesscom-stats-svg.vercel.app/stats?username=YourChessUsername` to your README! This older project will remain available but is no longer actively maintained.

# Chess.com Stats in Readme

![image](img/example.png "Example")

## Update your Readme

Add a these comment to your `README.md`:

```md
<!--START_SECTION:Chess-->
<!--END_SECTION:Chess-->
```

You can place these lines anywhere you want to display your chess ratings.

### Profile Repository

You'll need to get a [GitHub Access Token](https://docs.github.com/en/actions/configuring-and-managing-workflows/authenticating-with-the-github_token) with a `repo` scope and save it in the Repo Secrets by name `GH_TOKEN` , click [here](https://github.com/settings/tokens) to create an access token.

Here is a sample workflow file for running it:

```yml
name: Chess Stats Readme

on:
  schedule:
    # Runs at 12am IST
    - cron: "30 18 * * *"
  workflow_dispatch: # Run workflow manually (without waiting for the cron to be called), through the Github Actions Workflow page directly
jobs:
  update-readme:
    name: Update readme with chess stats
    runs-on: ubuntu-latest
    steps:
      - uses: Prathamesh-B/chess-stats-readme@master
        with:
          GH_TOKEN: ${{ secrets.GH_TOKEN }}
          CHESS_USERNAME: <Your chess.com Username>
          RATING_TYPE : <'best' or 'last'>
```

- Now you can commit and wait for it to run automatically.

## Flags

The following are the list of available flags:

| Option | Default Value | Description | Required |
|--------|--------|--------|--------|
| `RATING_TYPE` | last | Use your best or most recent ratings.(best/last) | No |
| `CHESS_USERNAME` |  | Your chess.com user name | Yes |
| `GH_TOKEN` | Your GitHub token with repo scope | Use this to configure the token of the user that commits the workflow result to GitHub | No |

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)

## Inspired From

[anmol098/waka-readme-stats](https://github.com/anmol098/waka-readme-stats)
