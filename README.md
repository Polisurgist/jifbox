![jifbox logo](http://assets.sunlightfoundation.com.s3.amazonaws.com/projects/jifbox/logo.png)

*Pronounced GIF-box*

JIFBOX is a web-based animated GIF photobooth. GIFs are generated in the browser using your webcam, then uploaded to various services that you can choose to enable (currently Dropbox and Tumblr).

![some people acting weird](https://raw.githubusercontent.com/sunlightlabs/jifbox/master/demo.gif)

**ONLY [GOOGLE CHROME](http://www.google.com/chrome/) IS SUPPORTED AT THIS TIME**

Want to see some GIFs generated by JIFBOX? Check out Sunlight Foundation's [Sunfright Tumblr](http://sunfrightgifs.tumblr.com) from our annual Halloween open house.

## Deploy

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/polisurgist/jifbox)

Click the button above to deploy on a new [Heroku](https://heroku.com) instance. You will be prompted for [configuration values](#environment-variables).

If you'd rather deploy somewhere else, you'll need to install MongoDB and the required Python packages listed in *requirements.txt*. You'll also need to set some [environment variables](#environment-variables). Refer to the [Flask Deployment Options](http://flask.pocoo.org/docs/0.10/deploying/) documentation for suggestions on running this app in production.

## Services

JIFBOX will automatically send the animated GIFs to various services, if you so choose. Support for each service must be enabled individually.

### Dropbox

Upload generated GIFs to a Dropbox folder. Requires **DROPBOX_KEY** and **DROPBOX_SECRET** to be set and Dropbox to be connected via */settings*. You can get these values by registering an app for the [Dropbox API](https://www.dropbox.com/developers).

### Tumblr

Post generated GIFs to a Tumblr blog. Requires **TUMBLR_KEY**, **TUMBLR_SECRET**, and **TUMBLR_HOSTNAME** to be set and Tumblr to be connected via */settings*. You can get these values by registering an app for the [Tumblr API](https://www.tumblr.com/docs/en/api/v2).

In the Tumblr API app settings set the Default callback URL to `http://[project_domain_name]/settings/tumblr/callback`

## Settings

Basic app configuration is done via environment variables. Additional settings for customizing the app are available at *http://\<your jifbox domain\>/settings*.

### Environment variables

#### Required

| Variable | Description |
|----------|-------------|
| ADMIN_PASSWORD | Password used for access to */settings* |
| MONGOLAB_URI | Heroku-style URL for MongoDB configuration |
| SECRET_KEY | String used to sign cookies and other security related things |

#### Optional

| Variable | Description |
|----------|-------------|
| BASIC_PASSWORD | **HIGHLY RECOMMENDED** If set, password required to use JIFBOX |
| DROPBOX_KEY | App key from the [Dropbox App Console](https://www.dropbox.com/developers/apps) |
| DROPBOX_SECRET | App secret from the [Dropbox App Console](https://www.dropbox.com/developers/apps) |
| TUMBLR_KEY | Consumer key for the [Tumblr API](https://www.tumblr.com/oauth/apps) |
| TUMBLR_SECRET | Consumer secret for the [Tumblr API](https://www.tumblr.com/oauth/apps) |
| TUMBLR_HOSTNAME | Full hostname for your Tumblr blog (ex: *this-is-my-blog.tumblr.com*) |