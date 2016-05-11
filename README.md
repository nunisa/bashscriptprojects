# bashscriptprojects
This repository reposits all the projects written in bash scripting language.<br>
Open Terminal and get it on your system by typing:-
<pre><code>git clone https://github.com/nunisa/bashscriptprojects.git</code></pre>

<strong>1. readThunderBox</strong><br>
<strong>readThunderBox</strong> reads thunderbird mail inbox and extracts the daily SVN commit messages and stores in a backup file which you can use as a daily activity record. It removes duplicate entries from the backup file, everytime you run the command. But sigh! There is a tradeoff between time and preformance as your mail inbox grows.<br>

Step by step instructions to configure <strong>readThunderBox</strong> on your system:-<br>
a) Check thunderbird hidden directory <pre><code>ls -al | grep “.thunderbird”</code></pre> which outputs <pre><code>drwx------   4 fw66 fw66      4096 Aug  6  2014 <span style=”color: #ff0000;”>.thunderbird</span></code></pre>
b) Change directory to .thunderbird and check the default mail configuration directory, e.g: <strong>w0tcfm06.default</strong> <pre><code>cd .thunderbird && ls</code></pre>
c) Change directory to Mail and check the configured domain names, e.g: <strong>mail.domain.in, mail.domain-1.in</strong> <pre><code>cd w0tcfm06.default/Mail/ && ls</code></pre>
d) Usually the mail domain with highest number (i.e. mail.domain-2.in in my case) should be the one currently in use. So, your final mail directory path should look something like this: <pre><code>/home/username/.thunderbird/w0tcfm06.default/Mail/mail.domain-x.in/Inbox</code></pre> where username is system username. To confirm please type the command:- <pre><code>whoami</code></pre>
e) Create one backup file of any name of your choice at home directory by typing the command:- <pre><code>touch yourBackUpFileName.txt</code></pre> and your backup file location will be <pre><code>/home/username/yourBackUpFileName.txt</code></pre>
f) Now, go to bashscriptprojects folder and open the <strong>readThunderBox</strong> file in your favourite editor and replace the line number 5 (i.e. fileOne initialization) with <pre><code>fileOne=”/home/username/.thunderbird/w0tcfm06.default/Mail/mail.domain-x.in/Inbox”</code></pre>
g) Replace line number 6 (i.e. backupFile initialization) with <pre><code>backupFile=”/home/username/yourBackUpFile.txt”</code></pre>
h) Replace line number 109 & 113 (i.e. monjit) with <strong>yourSVNusername</strong><br> 
i) Save the file changes and make <strong>readThunderBox</strong> a globally available command by typing:- <pre><code>sudo cp readThunderBox /user/bin/</code></pre>
j) Confirm it by typing:- <pre><code>whereis readThunderBox</code></pre> which outputs <pre><code>readThunderBox: /user/bin/readThunderBox</code></pre>
k) That's it...!!! You are all set to get important messages in your backup file by just typing: <pre><code>readThunderBox</code></pre>
l) Check yourBackUpFileName.txt<br><br>
<strong>2. clearYIIassets</strong><br>
<strong>clearYIIassets</strong> clears dynamically generated assets in YII framework.<br>

Step by step instructions to configure <strong>clearYIIassets</strong> on your system:-
a) Find out your workspace name. e.g. <strong>workspace</strong><br>
b) Find out in which directory is your <strong>workspace</strong> located. e.g. in home directory /home/username/workspace/<br>
c) Find out your project names. e.g. <strong>DEV_PROJECT_1 & DEV_PROJECT_2</strong><br>
d) So, your required directories should be something like this:- <br>
e) <strong>For Project 1</strong><pre><code>/home/username/workspace/DEV_PROJECT_1/assets</code></pre><pre><code>/home/username/workspace/DEV_PROJECT_1/assets/*</code></pre>
f) <strong>For Project 2</strong><pre><code>/home/username/workspace/DEV_PROJECT_2/assets</code></pre><pre><code>/home/username/workspace/DEV_PROJECT_2/assets/*</code></pre> where username is system username. To confirm please type the command:- <pre><code>whoami</code></pre>
g) Now, go to bashscriptprojects folder and open the <strong>clearYIIassets</strong> file in your favourite editor and replace line number 11 with <pre><code>firstProjectAssetsDir=$(echo "/home/username/workspace/DEV_PROJECT_1/assets")</code></pre> replace line number 12 with <pre><code>secondProjectAssetsDir=$(echo "/home/username/workspace/DEV_PROJECT_2/assets")</code></pre> replace line number 13 with <pre><code>firstProjectAssets=$(echo "/home/username/workspace/DEV_PROJECT_1/assets/*")</code></pre> replace line number 14 with <pre><code>secondProjectAssets=$(echo "/home/username/workspace/DEV_PROJECT_2/assets/*")</code></pre>
k) Save the file changes and make <strong>clearYIIassets</strong> a globally available command by typing:- <pre><code>sudo cp clearYIIassets /user/bin/</code></pre>
l) Confirm it by typing:- <pre><code>whereis clearYIIassets</code></pre> which outputs <pre><code>clearYIIassets: /user/bin/clearYIIassets</code></pre>
m) Change dirctory to your projects' assets directory (i.e not necessary, you can use this command from any directory). by typing:- <pre><code>cd /home/username/workspace/DEV_PROJECT_1/assets/</code></pre>
n) That's it...!!! You are all set to clear some useless assets by just typing: <pre><code>clearYIIassets</code></pre>
<strong>2. gitpush</strong><br>
<strong>gitpush</strong> is a combo git command to push local file changes to remote repository.<br>

Step by step instructions to configure <strong>gitpush</strong> on your system:-
a) Make <strong>gitpush</strong> a globally available command by typing:- <pre><code>sudo cp gitpush /user/bin/</code></pre>
b) Confirm it by typing:- <pre><code>whereis gitpush</code></pre> which outputs <pre><code>gitpush: /user/bin/gitpush</code></pre>
c) That's it...!!! You are all set to push some file changes to remote github repository by just typing: <pre><code>gitpush</code></pre>

<strong>TODO:</strong> Bug fixing.<br>
