# Fuse Fabric/Fabric8 environment promotion

This project is a simple set of maven modules + environment build module to illustrate how to use the built in maven plugins that come with [fabric8](http://fabric8.io/gitbook/index.html) that allow you to design an automated continuous delivery pipeline around your Fuse+Fabric deployments.

## What Fabric8 brings to the automation process
Fabric8 1.x brings a simple runtime grouping and provisioning model to allow you to quickly deploy and upgrade/downgrade your applications from a central dashboard/console across a fleet of machines. For this, you don't need to have any custom scripting/ansible/chef/puppet automation as the automation comes out of the box with Fuse/Fabric8. 

The central concept is a set of text-based properties files called **profiles** that declaratively describe the end-state of a deployment -- i.e., they describe what binaries, features, configurations, dependencies, etc that need to be deployed together. Profiles are versioned (to allow for rolling upgrades) and can have hierarchy relationships to cut down on duplication of configurations.  

## The Problem
In a shared environment where you have multiple teams working on different integrations/microservices/applications that each have their own timelines, deployment cycle, or pre-existing continuous integration cycles, deploying into a shared environment can result in collisions. We have to establish a convention for how applications make it into this environment, and be able to automate it/version it. One of the tenants of Continuous Delivery is to version everything, including application configuration, environment configuration, automation scripts, etc. so that environments can be recreated on the fly if necessary and avoid highly manually tailored environments which end up becoming very brittle and risky. 
 
With Fuse/Fabric8 profiles, **everything** is versioned in the built-in configuration management backend of Fuse/Fabric8, but how can those be recreated or how can those **profiles** be deployed into Fuse when applications change? And how can we do this within the constraints of applications deploying at different rates, different versions, different cycles, etc? 
  
## The Solution
A lot of automation is built into Fabric8 and this guide will attempt to show you how to best leverage it. Once you see what can be automated you'll say "ah, so I don't need all of these other scripts/tools to do this"? Let's take a step-by-step look. The focus of this guide will be fabric8 1.x, but more specifically JBoss Fuse Fabric 6.1 or 6.2. Some of the out-of-the-box features (I'll point them out along the way) are only available in the Fuse 6.2 versions, but can still be accomplished with the Fuse 6.1 environment (although, with some scripting)

Please visit my blog (http://blog.christianposta.com/fabric8/fuse-fabric-profile-migration-for-continuous-delivery/) for the rest of this step-by-step guide. Follow me on twitter @christianposta for more!