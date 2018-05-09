<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Starting or joining project</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="setup-or-clone-to-current-project">Setup or clone to current project</h2>
<p>We will show how to clone the project from bitbucket through git, sample used (BlueBird Automated Testing)</p>
<p>First we need set up the ssh key on your macOS</p>
<ol>
<li>From your terminal, enter ssh-keygen at the command line.</li>
</ol>
<pre><code>ssh-keygen
</code></pre>
<ol start="2">
<li>After entering above command, you will receive this message :</li>
</ol>
<pre class=" language-undefined"><code class="prism language-$ language-undefined">Generating public/private rsa key pair.  
Enter file in which to save the key (/Users/amaliya.sukma/.ssh/id_rsa):
</code></pre>
<ol start="3">
<li>Type exactly the same inside () :<br>
<code>/Users/amaliya.sukma/.ssh/id_rsa</code></li>
<li>Enter passphrase or your <code>sudo</code> password when prompted<br>
The command creates your default identity with its public and private keys. The whole interaction will look like this :</li>
</ol>
<pre><code>$ ssh-keygen  
Generating public/private rsa key pair.  
Enter file in which to save the key (/Users/emmap1/.ssh/id_rsa):  
Created directory '/Users/emmap1/.ssh'.  
Enter passphrase (empty for no passphrase):  
Enter same passphrase again:  
Your identification has been saved in /Users/emmap1/.ssh/id_rsa.  
Your public key has been saved in /Users/emmap1/.ssh/id_rsa.pub.  
The key fingerprint is:  
4c:80:61:2c:00:3f:9d:dc:08:41:2e:c0:cf:b9:17:69[emmap1@myhost.local](mailto:emmap1@myhost.local)  
The key's randomart image is:  
+--[ RSA 2048]----+  
|*o+ooo.          |  
|.+.=o+ .         |  
|. *.* o .        |  
| . = E o         |  
| o . S           |  
| . .             |  
| .               |  
| 				  |  
| 				  |  
+-----------------+
</code></pre>
<ol start="5">
<li>Go to the folder that contain ssh key, in this examples the folder is <code>/Users/amaliya.sukma/.ssh</code>, type the following command to your terminal :<br>
<code>cd /Users/amaliya.sukma/.ssh</code></li>
<li>list all file by type <code>ls</code>, it will show all files in the folder</li>
</ol>
<pre><code>localhost:.ssh amaliya.sukma$ ls
id_rsa		id_rsa.pub	
</code></pre>
<ol start="7">
<li>Copy your public key by :<br>
<code>cat id_rsa.pub</code><br>
it will show your key like this :</li>
</ol>
<pre><code>localhost:.ssh amaliya.sukma$ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDkfvPjPWfD/kkEnGlYOoGEtQXvAiDIazRJriJHl0NutRo2w6xsJyZ9Mnvzhu4eExx6i3/01f0Chgiz79Mqt0aaDrL/0XkAtk2i8EbFVwWTt6r61Cd8q02yHDpQwhirp1xSA7IrHWJ5CifKDUMerYzZXWHbfXoDefEHMGg0zOdU+YL0ThA519U3zSwv7thctE8fnhUIRb8ZuWxSJ/aPs40xpchXIZdEjT4DsSHPKu+5RH0I9r/CGJAzOyFX6xuogFCkNHa20SVEUhkPEQCHtz5aJazV2nMVJQ5342Kp3uHqxq4v3ZA2HWJWWcV23QXdAxdH/Giqc7hcI304MFArBm1p
</code></pre>
<ol start="8">
<li>Copy the result and it will be added to your bitbucket settings on the web</li>
<li>Go to <a href="https://bitbucket.org/icehousecorp/">https://bitbucket.org/icehousecorp/</a></li>
<li>At the bottom-left, click profile icon and choose <strong>Bitbucket settings</strong><br>
<img src="https://lh3.googleusercontent.com/gluSd8mUGYgrYXCoXNzYjKd2e80UKze85RMqDBMplkPeCrCqzJxOqaN1GUEwN5DxmGck2V2VQpQ" alt="bitbucket-settings" title="bitbucket-settigns"></li>
<li>Go to <strong>SSH Keys</strong><br>
<img src="https://lh3.googleusercontent.com/usi8uwSdW_A8NvHQ6uf3bUB6m-UFCo_U-oZoD1Eq1EvkzdsJ8oRBoNJA-oDWel3Z5BOfTl06gIk" alt="ssh-keys" title="ssh keys"></li>
<li>Click on <mark>Add Key</mark> and will be prompted with this, add your own label and add the <code>ssh-key</code> that previously you copied!<br>
<img src="https://lh3.googleusercontent.com/BMbUhZcfiVzhGZpkXi0rj7oyP7BJyh4up1WmS_SN1Uz9URx4jD7cMp-pxKWgGdSmF84lXBZywOY" alt="add key"></li>
<li>Save your key and move again to your terminal, try this command<br>
<code>ssh -T git@bitbucket.org</code><br>
if the command was successful, it will show this message:</li>
</ol>
<pre><code>localhost:.ssh amaliya.sukma$ ssh -T git@bitbucket.org
Warning: Permanently added the RSA host key for IP address '104.192.143.3' to the list of known hosts.
Enter passphrase for key '/Users/amaliya.sukma/.ssh/id_rsa': 
logged in as sukmaragilp.

You can use git or hg to connect to Bitbucket. Shell access is disabled.
</code></pre>
<ol start="14">
<li>All done and ready to test! Go on and clone your project to your local and start wonderful things with your own hand.</li>
</ol>
</div>
</body>

</html>
