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
          <li><a href="#run-the-action-manually">Run the action manually</a></li>
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
the same cookie in each.
<img src="https://files.catbox.moe/1bvc55.png">

<h3>Run the action manually</h3>
<img src="https://files.catbox.moe/jyhe5c.png">
And you're set! From now on Collei will claim any new codes and redeem the daily check-in rewards at Hoyolab for you every 6 hours!
<h2>Running locally</h2>
You can also run this repository locally if you do not wish to rely on GitHub.

```bash
$ git clone https://github.com/c4em/collei
$ pip install -r requirements.txt
$ GENSHIN_COOKIES="your cookies" STARRAIL_COOKIES="your cookies" ./collei
```

If you wish to automate this process, <a href="https://wiki.gentoo.org/wiki/Cron">read up on cron jobs for your distribution. </a>

<h2>Repository license</h2>
This project is licensed under <a href="https://www.gnu.org/licenses/gpl-3.0.en.html">GPLv3</a>. <br>
<img src="https://www.gnu.org/graphics/gplv3-with-text-136x68.png">
