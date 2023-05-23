<table>
  <tr>
    <td><image alt="Image of Collei reading" src="https://files.catbox.moe/9uextd.png"></td>
    <td>
      <h2>Collei</h2>
      Collei claims daily check-in rewards and new codes for you.
      <h4>Table of contents</h4>
      <ul>
        <li><a href="#setup">Setup</a></li>
        <ul>
          <li><a href="#fork-the-repository">Fork the repository</a></li>
          <li><a href="#copy-your-cookies">Copy your cookies</a></li>
          <li><a href="#create-a-repository-secret">Create a repository secret</a></li>
          <li><a href="#paste-your-cookies-in-the-repository-secret">Paste your cookies in the repository secret</a></li>      
          <li><a href="#give-the-action-write-permissions">Give the action write permissions</a></li>
          <li><a href="#run-the-action-manually">Run the action manually</a></li>
        </ul>
        <li><a href="#troubleshooting">Troubleshooting</a></li>
        <ul>
          <li><a href="#changed-password">Changed password</a></li>
          <li><a href="#setting-cookies-for-a-game-account-you-dont-have">Setting cookies for a game account you don't have</a></li>
          <li><a href="#something-else">Something else</a></li>
        </ul>
        <li><a href="#running-locally">Running locally</a></li>
        <li><a href="#repository-license">Repository license</a></li>
      </ul>
    </td>
  </tr>
</table>
<h2>Setup</h2>
<h3>Fork the repository</h3>
<img src="https://files.catbox.moe/dtuhxp.png">

<h3>Copy your cookies</h3>
Log in at <a href="https://hoyolab.com">hoyolab.com</a>, open the developer console by pressing <code>F12</code> on your keyboard and navigate to the console tab. Finally, paste the following in the console to copy your cookies to your clipboard <code>copy(document.cookie)</code>. <br> <br>
<img src="https://files.catbox.moe/te720c.png">
<b>IMPORTANT: Never share your cookies with anyone!</b>

<h3>Create a repository secret</h3>
<img src="https://files.catbox.moe/hfsub8.png">

<h3>Paste your cookies in the repository secret</h3>
Create a new secret called <code>GENSHIN_COOKIES</code> or <code>STARRAIL_COOKIES</code> respectively and 
paste your cookies. If both your Star Rail and Genshin accounts are connected to the same Hoyoverse account, paste
the same cookie in each. <br>
<b> If you don't have an account for one of the games, skip setting the cookie secret. Collei will only try to
claim the rewards for games you provide her with and may fail otherwise.</b>
<img src="https://files.catbox.moe/1bvc55.png">

<h3>Give the action write permissions</h3>
<img src="https://files.catbox.moe/4inzc8.png">
<img src="https://files.catbox.moe/hnovu2.png">

<h3>Run the action manually</h3>
<img src="https://files.catbox.moe/jyhe5c.png">
And you're set! From now on Collei will claim any new codes and redeem the daily check-in rewards at Hoyolab for you every 6 hours!
<h2>Running locally</h2>
You can also run this repository locally if you do not wish to rely on GitHub.

```bash
$ git clone https://github.com/c4em/collei
$ cd collei
$ pip install -r requirements.txt
$ GENSHIN_COOKIES="your cookies" STARRAIL_COOKIES="your cookies" ./collei
```

If you wish to automate this process, <a href="https://wiki.gentoo.org/wiki/Cron">read up on cron jobs for your distribution. </a>

<h2>Troubleshooting</h2>
Help! My Collei broke! <br>
This section goes over some common reasons why Collei might break.
<h3>Changed Password</h3>
If you reset your password, you'll have to set your cookies again because they'll be reset. Simply delete the existing secrets 
in the repository and follow the step to set your cookies again.
<h3>Setting cookies for a game account you don't have</h3>
Collei will fail if you provide her with cookies to a game you don't play. Simply remove the cookie for the
given game and she'll resume work like usual.

<h3>Something else</h3>
It could be that the script broke due to an oopsie on my side, in which case I'm sorry. Have a look at the 
<a href="https://github.com/c4em/collei">original repository</a> to see if there have been any changes. <br><br>
If there are, the easiest way to fix the issue, if you're not a developer, would be to set up collei again from scratch. <br>
Why? You might ask. I know it sucks but because GitHub does not allow you to have private forks of a repository,
which is why this repository is a template. If you do not care that you have to keep the repository public, you can use the 
fork option in the top right instead.
<br><br>
If there are not, you can contact me about the issue by opening an issue in the GitHub repository or sending me a message
directly somewhere. I'll be glad to help. My contact information is visible on my GitHub profile.

<h2>Repository license</h2>
This project is licensed under <a href="https://www.gnu.org/licenses/gpl-3.0.en.html">GPLv3</a>. <br>
<img src="https://www.gnu.org/graphics/gplv3-with-text-136x68.png">

