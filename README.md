# Identity Vault

This is Not the Rails codebase powering https://identity.hackclub.com!

This repository aims to be a proof-of-concept for an integration of Identity Vault with Canada Post's Identity+ service. It will likely never make it upstream, but where's the harm 

## contributing:
poke [annabel](https://hackclub.slack.com/team/U078HNSV750)!
avoid questions that can be answered by reading the source code, but otherwise i'd be happy to help you get up to speed :-D

kindly `bin/lint` your code before you submit it!
### areas of focus:
i think this is very self explanitory. i don't like hack club keeping my ID indefinitely, so imma fix it.
first up - integration with canada post's identity+ service, which lets me get verified at a local post office.

hopefully, i'll be able to work in the new digital credentials api as well, but i'll likely forget about this fork in 3-5 business days.

## dev setup:
- make sure you have working installations of ruby ≥ 3.4.4 & nodejs
- clone repo
- create .env.development, populate `DATABASE_URL` w/ a local postgres instance
- run `bundle install`
- run `rails db:prepare`
- console in (`bin/rails console`)
  - `Backend::User.create!(slack_id: "U<whatever>", username: "<you>", active: true, super_admin: true)`
- run `bin/dev` (and `bin/vite dev` if you want hot reload on css & js)
- visit `http://localhost:3000/backend/login`, paste that Slack ID in, and "fake it til' you make it"

## security

this oughta go without saying, but if you find a security-relevant issue please either contact me directly or go through the security.hackclub.com flow –
if you just open an issue or a PR there's a chance a bad actor sees it and exploits it before we can patch or merge.
