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
          <ul>
            <li><a href="#option-a-fork-the-repository">Option a: Fork the repository</a></li>
            <li><a href="#option-b-generate-from-template">Option b: Generate from template</a></li>
          </ul>
          <li><a href="#copy-your-cookies">Copy your cookies</a></li>
          <li><a href="#create-a-repository-secret">Create a repository secret</a></li>
          <li><a href="#paste-your-cookies-in-the-repository-secret">Paste your cookies in the repository secret</a></li>      
          <li><a href="#give-the-action-write-permissions">Give the action write permissions</a></li>
          <li><a href="#run-the-action-manually">Run the action manually</a></li>
        </ul>
        <li><a href="#using-docker">Alternative setup: Using Docker</a></li>
        <li><a href="#running-locally">Alternative setup: Running locally</a></li>
        <li><a href="#skip-daily-check-in">Skip daily check-in</a></li>
        <li><a href="#skip-claiming-codes">Skip claiming codes</a></li>
        <li><a href="#troubleshooting">Troubleshooting</a></li>
        <ul>
          <li><a href="#changed-password">Changed password</a></li>
          <li><a href="#setting-cookies-for-a-game-account-you-dont-have">Setting cookies for a game account you don't have</a></li>
          <li><a href="#cookie_token-missing">cookie_token missing</a></li>
          <li><a href="#geetest-triggered-during-daily-reward-claim">Geetest triggered during daily reward claim</a></li>
          <li><a href="#something-else">Something else</a></li>
        </ul>
        <li><a href="#repository-license">Repository license</a></li>
      </ul>
    </td>
  </tr>
</table>
<h2>Setup</h2>
First you'll have to make a decision, whether you want to fork Collei or generate your own version from the template. <br> <br>
Forking the repository has the benefit of being able to apply fixes and updates to your version easily, with the downside of having to 
have the repository publicly visible in your GitHub profile due to GitHub limitations. This is the recommended way if you do not know how to
manage a git repository.<br> <br>
If you wish to keep the repository private, you'll have to generate it from the template, with the downside of having to apply patches manually.
<h3>Option a: Fork the repository</h3>
<img src="https://files.catbox.moe/n75q20.png">
<h3>Option b: Generate from template</h3>
<img src="https://files.catbox.moe/dtuhxp.png">

<h3>Copy your cookies</h3>
Log in at <a href="https://genshin.hoyoverse.com/en/gift">genshin.hoyolab.com</a>, open the developer console by pressing <code>F12</code> on your keyboard and navigate to the console tab. Finally, paste the following in the console to copy your cookies to your clipboard <code>copy(document.cookie)</code>. <br> <br>
<img src="https://files.catbox.moe/te720c.png">
<b>IMPORTANT: Never share your cookies with anyone!</b>

<h3>Create a repository secret</h3>
<img src="https://files.catbox.moe/hfsub8.png">

<h3>Paste your cookies in the repository secret</h3>
If you play Genshin Impact, set a secret called <code>GENSHIN_COOKIES</code>, if you play Honkai Star Rail
set the cookie <code>STARRAIL_COOKIES</code>. You can also set both if you play both. If they are linked to 
different accounts, that is also fine, just repeat the previous step to obtain the cookie for the other account.
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
$ python -m venv venv
$ source ./venv/bin/activate
$ pip install -r requirements.txt
$ GENSHIN_COOKIES="your cookies" STARRAIL_COOKIES="your cookies" ./collei
```

If you wish to automate this process, <a href="https://wiki.gentoo.org/wiki/Cron">read up on cron jobs for your distribution. </a>

<h2>Using docker</h2>
<a href="https://github.com/c4em/collei/issues/4">The process is documented here</a> by <a href="https://github.com/SleepingPanda">@SleepyPanda</a>.

<h2>Skip daily check-in</h2>
If you wish to skip the daily check-in due to issues like the Geetest captcha, simply <a href="https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository">create a new configuration variable</a> called `SKIP_DAILY` and assign it any value.
<h2>Skip claiming codes</h2>
If you wish to skip claiming codes, simply <a href="https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository">create a new configuration variable</a> called `SKIP_CODES` and assign it any value.
<h2>Troubleshooting</h2>
Help! My Collei broke! <br>
This section goes over some common reasons why Collei might break.
<h3>Changed Password</h3>
If you reset your password for any reason, you will have to set the secrets again, as the previous cookies will be invalidated.
Simply delete the existing secret and follow the prior steps again to resolve the issue.

<h3>Setting cookies for a game account you don't have</h3>
Collei will fail if you provide her with cookies to a game you don't play. Simply remove the cookie for the
given game and she'll resume work like usual.
<h3><code>cookie_token</code> missing</h3>

Head over to <a href="https://genshin.hoyoverse.com/en/gift">genshin.hoyolab.com</a>, open the developer console using `F12` and switch to the storage tab, from there
navigate to cookies and select and copy the value of `cookie_token` or `cookie_token_v2`. You will have to append this to the previous cookies you have copied like
this: `[previous cookie]; cookie_token=[copied value]`. The semicolon is important, don't leave it out. If you copied `cookie_token_v2` set that instead of `cookie_token`.

<img src="https://files.catbox.moe/6aw2ko.png">

<h3>Geetest triggered during daily reward claim</h3>
If you don't care about the daily check-in and just want Collei to claim codes you can avoid this issue entirely by <a href="#skip-daily-check-in">skipping daily check-in</a>.
This means that your account might have been flagged for automated claiming of rewards, which will result in you
having to complete a captcha to claim the reward. Sometimes just running Collei again will resolve the issue.
If the issue does not go away, it might be useful to try and  <a href="https://docs.github.com/en/actions/using-workflows/disabling-and-enabling-a-workflow">disable Collei</a> 
for a week or so and claim the rewards manually while solving captchas and then cycle Collei back on.

<h3>Something else</h3>
It could be that the script broke due to an oopsie on my side, in which case I'm sorry. Have a look at the 
<a href="https://github.com/c4em/collei">original repository</a> to see if there have been any changes. <br><br>
If there have been any changes and you've forked the repository, you can simply head over to your fork, above the file browser
there should be a message stating that your version is behind by X commits, click on that text, then on the top right it will
say "merge", press that and follow the trail of green buttons to get it automatically applied.
<br><br>
If you generated your repository from the template and you do not know your way around git, the simplest way to update your
version of Collei would be to set it up again, if you do know your way around git, simply generate a patch file from the 
latest changes and apply them to your version.
<br><br>
If there are no changes, open an issue on this repository detailing your issue and I will look in to it.

<h2>Repository license</h2>
This project is licensed under <a href="https://www.gnu.org/licenses/gpl-3.0.en.html">GPLv3</a>. <br><br>
<img src="https://www.gnu.org/graphics/gplv3-with-text-136x68.png">

