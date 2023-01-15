# Docs_CL
Creating a documentation for all the tools I've used across different platforms
- Github README.md file writing syntax [here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)






## Github
SSH access setup for your local repository. Reference link [here](https://medium.com/hackernoon/step-by-step-guide-to-push-your-first-project-on-github-fec1dce574f)


1. IMPORTANT: After running the line of code below, you don't use the default "home/roar/.ssh/id_rsa". Use your name as a path_id to prevent others from overwriting eg.: "home/roar/.ssh/chris_id_rsa"
    ```
    ssh-keygen -t rsa -b 4096 -C "[YOUR EMAIL]"
    ```
2. Start a new instance of the ssh-agent program and set the apporpriate environment variables for the current shell session. "-s " option is to run it in "silent" mode, which causes it to print the commands needed to set the environment variables to standard output, rather than executing them directly. The `eval` command runs the commands printed by the ssh-agent.  
    ```
    eval "$(ssh-agent -s)"
    # it gives like {{agent_id : 15800}}
    ```

3. Add SSH Private key to ssh-agent
    ```
    ssh-add ~/.ssh/[YOUR SSH_ID FOLDER]
    ```

4. LAST STEP (Important) Now goto github.com ➢➢ Under Profile Photo (Drop Down) ➢➢ Settings ➢➢ Use SideBar {{ SSH & GPG Keys }} ➢➢ Then go to this directory on your computer {{~/.ssh/[YOUR SSH_ID FOLDER]}}. Open this file and copy your .pub (public) key.

5. Now for Testing SSH Connection.
    ```
    ssh -T git@github.com
    # Hi {{ USERNAME }}! You've successfully authenticated but github does not provide shell access.
    ```

If you run into issues like `ERROR: Permission to [GITHUB_USERNAME]/[GITHUB_REPO].git denied to [NOT YOU].`, redo steps 2 - 5 in your local github repository terminal shell





## Ubuntu Operating System
- To check if a package is installed,
```
dpkg -l [Package Name]
```






## Youtube DL
YoutubeDL main hub [here](https://github.com/ytdl-org/youtube-dl)
ChatGPT inquiry link [here](https://chat.openai.com/chat/5eb88024-7e28-4815-9333-a6831b68bf8c)
- The tool is hidden path is `/home/chris/.youtube-dl`
- Use download.sh to install a list of files in url.txt (newline separated urls)
```
./download.sh
```
- To download a list of files, open download.sh






## TeamViewer
- If TeamViewer is not working, SSH into computer. 
```
sudo teamviewer --daemon stop
sudo teamviewer --daemon start
sudo teamviewer --daemon restart

# Or sometimes, teamviewer return comment will recommend running:
systemctl

# For purely using SSH to initiate teamviewer, we need to first set the default password for future connections.
sudo teamviewer passwd [PASSWD]
```

- get the teamviewer ID from running:
```
sudo teamviewer info
# sudo is needed because if not, it does not have permissions to view the ID
```
- If that still persists:
	- Find the process_ID and pkill it
	- A few ways to do this:
	```
	# Finding the Process_ID
	
	ps aux | grep -i “keyword of name of desired program”
	
	# OR
	
	pidof program_name
	
	# AND Kill it with
	
	pkill -u process_ID
	
	# OR
	
	sudo kill -9 process_ID
    ```

	# The difference:
	kill -9 sends a signal called SIGKILL to the process with the specified process ID, which immediately terminates the process. pkill -u is used to kill all processes running under a specific user with the specified process ID. The -9 option is not required when using pkill. Additionally, pkill allows for more flexibility in selecting processes to be terminated, such as by name, terminal, or other criteria.

	
