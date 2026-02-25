# Modules

This repository is intended to add new third party JASP modules.
If anything is unclear just send us a message on our mattermost server or by making an issue [here](https://github.com/jasp-stats/jasp-issues/issues)

## How to add a new module

- fork this repository
- add a new `yaml` file in `modules-metadata` folder with the following structure:

```yaml
name: "ModuleName" 
gitUrl: "Your JASP module git repository"
```

- create a pull request to this repository
- after review, and successful merge, your module will be added to the `beta-modules` folder

## How to update a module

- Make a PR on our fork of your module jasp-stats-modules/<your module name> (eg [jasp-stats-modules/jaspAnova](https://github.com/jasp-stats-modules/jaspAnova))
