See the rendered site: http://www.uiko.de (temporary name, I had this domain name sitting around).

To run this:

    bundle install
    bundle exec middleman

PR's encouraged.

To add videos for an event:

- Add the videos to `data/videos.yml`. Let's keep this yml file sorted by date. Also look at `data/events.yml` and `data/speakers.yml` and add the missing information there. Here's an [example PR](https://github.com/chriseidhof/ios-videos/pull/12).
- Currently, we only support youtube. However, it should be easy to add support for other platforms (e.g. vimeo). Let me know if this is an issue. Or even better, file a PR that adds vimeo support.

If you want to import an entire YouTube account, you can run `bundle exec rake fetchyt[uikonf]` (replace `uikonf` with the name of the YouTube account). To do this, you need to create a `.env` file with a YouTube API account in there. You will need to edit the generated YAML before copy-pasting it into `videos.yml`.

### Troubleshooting

If you get the following error:

    An error occurred while installing eventmachine (1.0.8), and Bundler cannot
    continue.
    Make sure that `gem install eventmachine -v '1.0.8'` succeeds before bundling.

please perform the following command:

    $ gem install eventmachine -v '1.0.8' -- --with-cppflags=-I/usr/local/opt/openssl/include

### For maintainers

Run `rake publish` to build the site and publish it to GitHub Pages.
