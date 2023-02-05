# Defaut-mic
### How to make some of your input device as default

#### Look which of these is your input device that I set as default

To do this we must type the code below

~~~bash
pactl list short sources
~~~

Should return something like this

![Screenshot from 2023-02-05 17-20-26](https://user-images.githubusercontent.com/78699072/216842781-d493eaa0-dbbd-4085-8472-f256f529071e.png)

you should check the one with "stereo" in the forum, in my case it's item 3

### How do i set it as defaulthow do i set it as default

let's create a .sh file to put the script in it, we can create using touch or gedit, example:

##### Gedit:

~~~bash
gedit mic.sh
~~~

##### Touch:

~~~bash
touch mic.sh
~~~

After that it will create a mic.sh file, open it.

![Screenshot from 2023-02-05 17-34-50](https://user-images.githubusercontent.com/78699072/216843456-b0f3b1bb-59cf-44f1-abad-15ef67a8785f.png)

After that put the command below to set the pattern in my case it was 'alsa_input.pci-0000_00_1f.3.analog-stereo'

~~~bash
#!/bin/bash 
pactl set-default-source 'PUT HERE YOUR MIC THAT YOU LOOKED AT IN THE STEP ABOVE in my case is alsa_input.pci-0000_00_1f.3.analog-stereo'
~~~

##### Yours should look like this or similar

![Screenshot from 2023-02-05 17-47-20](https://user-images.githubusercontent.com/78699072/216844986-41d6e927-fe7f-4ba8-b2c8-b673ff313894.png)

Save and close the file.

#### Permission mic.sh

now gave permission for the mic.sh you just created

~~~bash
sudo chmod +x mic.sh
~~~

Enter the code above and enter your password to allow mic.sh

#### Startup

Make it start together with the system.

Open Startup Applications on your computer

![Screenshot from 2023-02-05 17-55-54](https://user-images.githubusercontent.com/78699072/216845326-68f27e5a-d7c8-4a9b-a360-c79793987ba8.png)

After opening the Startup Applications click on "Add" and the following page will appear

![Screenshot from 2023-02-05 17-59-58](https://user-images.githubusercontent.com/78699072/216845497-6d0f560e-aec7-4073-90a7-9f55a9b75236.png)

Add the changes above and you're done


