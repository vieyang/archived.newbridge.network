# Configs Readme

NewBrige Project website will be using [Hugo](https://gohugo.io) to generate static site with custom configurations, features and theme.

`/.configs` will be the hugo configuration directory and custom files for the website. 

To use a seperate directory like this is convient to manage and update Configs, Features and Themes aside from the actual website contents. And the contents directories are placed in `/contents` and `/contents-language-specified`. 

These will results in contributors focus on the contents only don't have to care about the developer contributors focus in this directory. And also helps to keep the commits history belongs to each directory.

## Current Working Progress and won't run here

Currently this config won't run in any environment since it's lack of other supporting files like archetypes, layouts and theme required for a complete hugo project.

Those files are currently in multiple seperate repos for development and haven't gathered up yet.

They will be added to here once the developments are complete to be merged together.