**DO NOT USE THIS ON GITHUB CODESPACES. THIS GUIDE IS FOR YOUR LOCAL MACHINE**

# SSH Protocol Port Forwarding

## Features

- Forwarding services that run on specific ports to a different computer
- Evade many site restrictions using a proxy in the mix
- Code, manage, etc your local machine

## Info
- You will need some sort of Linux knowledge to use this guide.
- Any issues you find, you can create a issue request and I will try to help.
- Any help you want, or suggestions, use the discussions.
- I will not be at fault if you get in trouble for anything YOU do.
- I do not endorse you use this, but here it is for those who do.
- Learn to install Linux guide: `https://www.youtube.com/watch?v=_BoqSxHTTNs`

## Instructions

**THIS WILL ONLY WORK IF YOU HAVE A WINDOWS OR MAC OR LINUX COMPUTER AS WHAT YOU ARE GOING TO USE TO CONNECT TO YOUR MACHINE AT HOME** **DO NOT FOLLOW THESE INSTRUCTIONS UNLESS YOU DO**

1. Install Ubuntu 24.04 or any other Linux version that supports openssh on a computer. (Documentation written with Ubuntu 24.04). Install either the GUI or server version. There are many tutorials on how to install Linux.
2. Be sure you know the password to your machine. If not, we must do tricking. Go to the bypassing password section in this readme, finish those steps, then continue.
3. Install openssh-server using the following command `sudo apt update && sudo apt install openssh-server`. This will install SSH to your machine. Then run `sudo systemctl start ssh && sudo systemctl enable ssh` to have SSH start on boot and start SSH now.
4. Customize OpenSSH to your liking using this command `sudo nano /etc/ssh/sshd_config`. If you want to change the port it runs on, unhashtag the PORT line and change 22 to any port you like.
5. Port forward on your router the port you have set SSH to. Using Deco, you can go to the Advanced Settings -> Nat Forwarding -> Port Forwarding, then creating a new forward and selecting your machine and forwarding the port of SSH. You can use a video on the internet to learn how to port forward based on your router.
6. Almost done! Now install any service you want. If you want Interstellar with this readme, run `sudo apt update && sudo apt install git -y && sudo git clone https://github.com/cleverman606/portwarp.git`. This can be any service that you know the port it runs on that serves a webpage. It could even be a local HTML project you are working on though the steps would change.
7. We are done now! You have cloned the repo you would like to use to serve a site on a different computer than the one you are using! A couple steps left to fullfill this though. You have to SSH into your machine from your target computer you want to use your proxy or other service. We do this with this command in Powershell,  Command Prompt, or Terminal: `ssh -p <the port you chose, if you didn't select a different port, DO NOT USE THE -p FLAG> -L 8000:localhost:8000 <user of linux machine>@<the ip of where your machine is located>`. The 8000 is the port of the service you are going to run, and the port you will use on your machine to access it. If you change one, it is recommended to change the other.
8. Your done! After entering your users password, you should be in the linux command prompt. Don't be scared, everything is easy. run these simple commands: `ls`, then `cd <the directory of your service listed in the ls command. if it doesnt exist, do step 6 again, but inside of the SSH>`.
9. Almost there! Now you are in the directory of your service! So close! Run: `npm start` or any other command you use to start your service (be sure to follow the service you are using's instructions.). If you simply going to code, make sure you have python installed `sudo apt update && sudo apt install python3` and then run `python -m http.server <the port you selected when running SSH>`. Most of the time, after running `npm start` or any other command to start your service, it will feed something like this: `Server started on, localhost:5000`. The 5000 is the port. After finding that, hold `ctrl + c` until the service stops and you are back to running commands, type `exit`.
10. You know the port now, very important. Next, run step 7 again, but change the two 8000's to the port of the service you started when it fed it out. It should have looked something like this: locahost:**5000**. That number is the port.
11. You are back into your machine AGAIN! Do step 8 again, and then run `npm start` or whatever else the services documentation says to start your service. Now, on the computer you have used to SSH, go to `locahost:<the port you used when SSHing into the machine>`. It should have worked! If it didn't feel free to open an issue or discussion, and I will try to help as well as possible.

## Bypassing Password
**If you are using lets say your father's Linux PC, this will be complicated to get a user on their PC with sudo privileges.**

1. If you are ready, first, get them to open a terminal window, and run `sudo apt update`. This is a simple command, and the start of our exploit. This command updates the package list, but has them use their sudo password. After they run this, be sure they do not close the terminal window. The command sudo is weird. When someone runs a sudo command, the sudo command is open to anyone until the terminal window closes.
2. Be sneaky, when they are not there, be sure the terminal window from before is still open, run these 2 commands: `sudo adduser <change this to your user you want>` Spam enter until you are done with the questions they ask you. Then, run `sudo usermod -aG sudo <the username you just made>`. This gives your user sudo privilges.
3. Change the password to your user. Make sure you still have the terminal window open, run `passwd <the user you made here>`. It will ask your for a password to set, be sure to remember this, and it will NOT show you what you are typing, BE 100% sure you have it correct, if it says BAD PASSWORD after clicking enter, but still says Confirm Password, ignore the BAD PASSWORD warning. Just retype the password you made.
4. You now have your sudo user! You can go back to instructions step 3 and complete them while you still have the sudo terminal access.

# Interstellar

## Features

- About:Blank Cloaking
- Tab Cloaking
- Wide collection of apps & games
- Clean, Easy to use UI
- Inspect Element
- Various Themes
- Password Protection (Optional)
- Built-in Tab System
- Now.gg Support
- Fast Speeds
- Geforce NOW Support

## Deployment

> [!IMPORTANT]
> You **cannot** deploy to static web hosts, including Netlify, Cloudflare Pages, and GitHub Pages.

### Password Protection

1. Go to the `config.js` file and set `challenge` to **true**. Then, set the environment variable as follows:
2. For PNPM: Run either `config=true pnpm start` or `$env:config=true; pnpm start`, depending on your server.
3. For Bun: Run either `config=true bun start` or `$env:config=true; bun start` if you prefer Bun.
4. For NPM: Run either `config=true npm start` or `$env:config=true; npm start` if you prefer NPM.
