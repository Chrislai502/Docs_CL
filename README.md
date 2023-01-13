# Docs_CL
Creating a documentation for all the tools I've used across different platforms
- Github README.md file writing syntax [here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

### Youtube DL
YoutubeDL main hub [here](https://github.com/ytdl-org/youtube-dl)
ChatGPT inquiry link [here](https://chat.openai.com/chat/5eb88024-7e28-4815-9333-a6831b68bf8c)
- The tool is hidden path is `/home/chris/.youtube-dl`
- Use download.sh to install a list of files in url.txt (newline separated urls)
```
./download.sh
```
- To download a list of files, open download.sh

### TeamViewer
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
	
	# The difference:
	kill -9 sends a signal called SIGKILL to the process with the specified process ID, which
	immediately terminates the process. pkill -u is used to kill all processes running under a
	specific user with the specified process ID. The -9 option is not required when using pkill.
	Additionally, pkill allows for more flexibility in selecting processes to be terminated, such as
	by name, terminal, or other criteria.
	```
	
