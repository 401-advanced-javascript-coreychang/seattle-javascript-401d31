# DEMOS - Component Based UI

For this class, work all demos locally instead of at Code Sandbox. You'll definitely need to be running tests, builds, creating documentation, etc.  This is a great opportunity to demonstrate developing React Apps outside of the online IDE and in a more "Real" way.

## Documentation

* Install Styleguidist
* Start the doc server
* Write a simple doc for a component
* View it live
* Run the build
* View it statically
* Add a script to package.json to build it in the wild


## Testing `/demo/tdd`

### Enzyme Testing

The key part of the demo here is to wire up the `setupTests.js` file in the `src` folder.  This has the requisite imports and globals declared. What create-react-app (and sandbox) does is to incorporate that into every test file you write, which is a nice time-saver.

Focus your demo on the differences between and use-cases for `shallow()` and `mount()`. Our demo code uses both of those in different ways.

This can be done at sandbox, but to go deeper (and to connect into a CI environment, you'll need to work from a repo).  This is an annoying step, but it's important to start at sandbox and get all of the goodness of visual TDD.  In the next stage, we'll go local and the students will start to see what local react dev looks like and how to operate in a CI/CD world

### Snapshot Testing

You cannot snapshot test on Code Sandbox because it creates files, so all of this needs to be done locally.

Pull down your sandbox locally and install everything. You'll need to add the `react-test-renderer dependency`  module.

Write the snapshot test as shown in the demo, and then as you run `npm test` you can observe the new snapsots folder being created and the json file within it.

Note that this is a comparison of raw html.  How could this break? What if you added a className to one of the elements? The enzyme (behavior) test would probbly still be ok, but adding a class would change the markup and therefore break the snapshot. This is a potentially big deal.

## Travis hookup
At this point, you should be able to check this into github and have Travis pick it up. 

* Make sure you're actually working in a repo (create one if not)
* Pull in a .travis.yml file and ensure that its setup to do an `npm test` (and not a `lint` unless you've also set that up)
* Check into master and observe it passing at Travis-ci.com

---

**This is a good time for a break!**

---



## AWS Deployment - S3

At minimum, the goal is to deploy a website to an AWS bucket.

First, get back to your command line and add the `node-sass` dependency (assuming you've got some sass in your demo code) and then run `npm run build`

Now, we have a `build` folder. This is a great opportunity to dive back into what React really is. Yes, we run a server to do our dev work locally.  Yes, codesandbox.io is a server that runs react as an app. But in reality, React is a static app.

Create yourself an S3 Bucket, give it public permissions, upload your build folder contents, and tick the "Website" switch and you should be able to simply view your react app.

## AWS Deployment - Cloudfront

Use the aws.yml template file and create a new cloud formation stack by uploading it. Once you do that, it'll take about 20 minutes for it to pull from github.

Talk through the contents and purpose of this .yml configuration file, which is to instruct AWS to do all of the necessary steps for you.

You can automate the creation of this file by using a tool created by Code Fellows:

[AWS React Pipleline Configurator](https://www.npmjs.com/package/@johnfellows/aws-tools)

Once a .yml file is created, you should be able to upload it to cloud formation and see your app deployed ina bout 30 minutes.

## Netlify Deployment

Netlify is a static site hosting platform that is essentially an S3 system.

* Create a Netlify Account
* Hook to your github
* Run the build script, specifying the build folder
* Win


