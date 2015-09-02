# Read me

A little helper allowing you to `Cmd`-click on files in [iTerm2](https://www.iterm2.com/) and open them in [IntelliJ IDEA](https://www.jetbrains.com/idea/). 

## TL;DR

IntellJ actually comes with a way to open a file from the commandline. However, unfortunately it requires parameters to be passed in a specific way – which obviously is not compatible with how iTerm2 expects you to pass parameters to applications you register to open files:

* The line number must be be passed with a `--line` arguments, which – admittedly – is something you can do with iTerm2's options, like this: `--line \2`.
* *If and only if* you pass line numbers, then you *also* need to pass the location of the project. No idea why. But that means you need to look at a file and find the location of the root of the project by walking up the directory hierachy. Absolutely something you cannot do in a oneliner in iTerm2. 

## Usage

### Step 1: installing it

You will first of all have to install it:

```bash
npm install -g idea
```

Just to be sure: this doesn't install IntellJ (doh). It does however install the `idea` command. 

### Step 2: configuring iTerm2 to use it

I'll advise you to first create a new profile. Then in the **Semantic history** section of the profile, select the `Run command` option and enter
`idea "\1:\2"` as the command. You will notice that I actually have that preceeded by `. ~/.zshrc`, which is making sure my [nvm](https://github.com/creationix/nvm) environment is configured before running this.

### Step 3: there is no step 3

That's it. You should now be able to command click on file links in the terminal and have them opened in IntelliJ.


