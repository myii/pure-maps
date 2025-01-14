# Ubuntu Touch Packaging

## Preparations

Install [Clickable](http://clickable.bhdouglass.com/en/latest/install.html)
which is used to build and publish click packages.

Also copy `tools/apikeys_dummy.py` to `tools/apikeys.py` and fill missing API
keys for the services that you plan to use.

You may want to create a symlink to the config file to omit the `-c` flag in
all clickable calls:

    ln -s packaging/ubports/clickable.json clickable.json

Otherwise you'll have to append `-c packaging/ubports/clickable.json` to all
clickable commands.

## Dependencies

Run the following command to download and compile the app dependencies:

    clickable prepare-deps build-libs

If you'd like to debug on desktop, too, also compile the dependencies for amd64:

    clickable prepare-deps build-libs --arch amd64

## Building

Build the app by running

    clickable build click-build

## Debugging

To debug on a Ubuntu Touch device simply run

    clickable

To debug on the desktop run

    clickable desktop

See [Clickable docs](http://clickable.bhdouglass.com/en/latest/) for details.
