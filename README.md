# Rails Reload Issue

- **Working** Docker Community for Mac `2.3.0.5`
- **Broken** Docker Community for Mac `2.4.0.0`

# Instructions to Reproduce

1. Run `docker-compose up --build`
1. Visit `http://localhost:3000`
    - See words `DELETE ME`
1. Edit `views/posts/index.html.erb`
    - Remove words `DELETE ME`
1. Refresh
    - If running `2.3.0.5`, words will disappear.
    - If running `2.4.0.0`, words remain.

### Docker Community 2.4.0.0

While on `2.4.0.0`, you can force refresh to work by swapping file watchers.

  1. Search for `SWAP_FILE_WATCHER`
  1. Swap lines so `FileUpdateChecker` is active
  1. Restart container & rerun instructions above
