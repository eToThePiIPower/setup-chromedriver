# setup-chromedriver

A simple action to install chromedriver and chromium from Ubuntu's `.deb` pool.

Because modern versions of Ubuntu (19.10 and higher) don't support installing
Chrome or Chromium from the apt repository; and because installing from snap
doesn't work from inside the GitHub Action Docker containers; we need a
round-about way to install one of these browsers so it can be used with
chromedriver for acceptance testing. 

This action collects this process as a simple single step. It:

  * Runs an `apt-get update`
  * Downloads the `.deb` files from [ archive.ubuntu.com ](http://archive.ubuntu.com/ubuntu/pool/universe/c/chromium-browser/)
  * Installs the `.deb` files

## Using

Add this to your `workflow.yml`

  ```yml
  - uses: etothepiipower/setup-chromedriver@v1
    with:
      chromium-version: '101.0.4951.64-0ubuntu0.18.04.1' # default
  ```

## Valid versions

Only two values are currently available that work (at least on `ubuntu-20.04`
and `ubuntu-latest` )

   * `101.0.4951.64-0ubuntu0.18.04.1` (default)
   * `90.0.4430.72-0ubuntu0.16.04.1`
