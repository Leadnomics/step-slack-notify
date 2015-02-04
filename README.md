# step-slack-notify

[![wercker status](https://app.wercker.com/status/532b17911c240b777d000a01 "wercker status")](https://app.wercker.com/project/bykey/532b17911c240b777d000a01)

Send a message to a Slack channel after build or deploy

## Options

### required

> This variables can be set at the step on your ```wercker.yml``` file or at the deploy targer variables. Just declare them like: ```WERCKER_SLACK_NOTIFY_SUBDOMAIN```, ```WERCKER_SLACK_NOTIFY_TOKEN``` and ```WERCKER_SLACK_NOTIFY_CHANNEL```

- `subdomain` - Your Slack team subdomain.
- `token` - Your slack integration token.
- `channel` - The Slack channel you want to push messages for.

### optional
- `begin-notice` - Set to true when you want to alert when a build/deploy has begun and thus don't know whether it passed or failed yet
- `slack-icon` - Icon to use for slack
- `passed-message` - Use this option to override the default passed message
- `failed-message` - Use this option to override the default failed message
- `passed-images` - A comma-delimited list of images to add to the passed or failed message...One will be choosen randomly.  For funsies
- `failed-images` - The same, only when the build fails

## Example with step variables

```yml
build:
	after-steps:
		- slack-notify:
			subdomain: "testapp"
			token: "YOUR SLACK TOKEN"
			channel: "general"
```

## Example with wercker deploy target variables

```yml
build:
	after-steps:
		- slack-notify:
			subdomain: $WERCKER_SLACK_NOTIFY_SUBDOMAIN
			token: $WERCKER_SLACK_NOTIFY_TOKEN
			channel: $WERCKER_SLACK_NOTIFY_CHANNEL
```

