# Epochs (EASY)

An Easy machine from try hack me with Os command injection vulnerability. On looking at the machine description we have a hint in the description.



![screenshot-Thu-09-21-48](https://user-images.githubusercontent.com/115337317/213351498-d0d43fe1-36c0-433a-a512-39e741af3456.png)

Afterreading the line we can have an idea that the input on the website is directly passed to the command line. Let's start the machine and explore the website to get our flag.

![targetsite](https://user-images.githubusercontent.com/115337317/213351968-91b8fb11-550d-4cd5-b6f3-6d6643a94523.png)

So this is our simple website with a single input page where we input epochs and get UTC data. Like this 

![testingsite](https://user-images.githubusercontent.com/115337317/213353862-576083c8-e1ea-4ae3-9af6-acfdb623f011.png)

But If we recall our description we know that the input is directly passed to the command line.

Example:- `$ your epochs`

`UTC-output` 

Now let's try something called concatenation. We try to concatenate our command with another command and analyze our result.

Windows: ;
Linux: && 

Our command will be like this for windows `100000000 ; whoami`  and for linux `10000000 && whoami`.

After running both commands in the input we get our result by the Linux command. This confirms two things first the target system is Linux and our command injection is successful so we can retrieve data.

![checkingcommandinjection](https://user-images.githubusercontent.com/115337317/213353223-fec2cc52-167d-4b0b-9ca6-bad58f549fad.png)

Now can explore more in the machine and retrive our flag.

![ls-al](https://user-images.githubusercontent.com/115337317/213353321-ec37c026-bc9c-4b78-a603-fefb25e0746e.png)


THM MACHINE HINT:-The developer likes to store data in environment variables, can you find anything of interest there?

By this hint, we know that the flag is somewhere in the system variables. We will do a simple search in google `how to see system variables in Linux machine` and we can see that there are two commands which we can use to see system variables `env` or `printenv`. On executing `1000000 && printenv` we get our flag.

![flag](https://user-images.githubusercontent.com/115337317/213353999-1207e11e-31a2-438b-b955-3d2495db2afd.png)

This machine teaches us about how we can exploit simple input areas in a website to retrieve some sensitive variables using command injection.
