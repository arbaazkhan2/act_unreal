
## How to train
First, download and install DeepMind Lab
```
$ git clone https://github.com/deepmind/lab.git
```
Then build it following the build instruction. 
https://github.com/deepmind/lab/blob/master/docs/build.md

Clone this repo in lab directory.
Add this bazel instruction at the end of `lab/BUILD` file

```
package(default_visibility = ["//visibility:public"])
```

Then run bazel command to run training.
```
bazel run //act_unreal:train --define headless=glx
```
`--define headlesss=glx` uses GPU rendering and it requires display not to sleep. (We need to disable display sleep.)

If you have any trouble with GPU rendering, please use software rendering with `--define headless=osmesa` option.

## How to show result

To show result after training, run this command.
```
bazel run //act_unreal:display --define headless=glx
```
