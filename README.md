# QuickPaste v2.0
QuickPaste is a paste tool based on the open-source Ghostbin Project, or also known as Spectre. But with slight modifications to make it run smoother on DigitalOcean App.

This repo is the exact same as the original Spectre repo, but with slight improvements so that you can fork it and deploy it using DigitalOcean App in seconds.

# System Requirements

- 1 GB Ram (4 GB Recommended for Stability)
- 1 vCore CPU (2 vCores Recommended For Stability
- 16 GB Storage (64GB+ Recommended if you want your site to be public and store thousands of pastes)

# Installation Guide

For this install tutorial, I will be using Ubuntu 20.04. If you are using a version that's lower than this, you must update to make sure everything runs smoothly
However, if your version is the same or higher than this then you can follow this tutorial normally, so let's get started!


1. Install Go on your Server using the following code:

<code class="language-shell hljs">cd /usr/local
wget https://dl.google.com/go/go1.14.linux-amd64.tar.gz
tar -C /usr/local -xzf go1.14.linux-amd64.tar.gz</code>

Add to the bottom of your <code>/etc/profile</code> file with

<code class="language-bash hljs"><span class="hljs-built_in">export</span> PATH=<span class="hljs-variable">$PATH</span>:/usr/local/go/bin</code>

You can either also run that at your command prompt or logout and log back in.

2. Install Mercurial and Python Pygments:

<code class="language-shell hljs">apt install mercurial python3-pygments</code>

3. Install ansi2html:

<code class="language-shell hljs">apt install python-pip
pip install ansi2html</code>

4. Install Git, I like to compile it myself so I get the latest version:

<code class="language-shell hljs">cd /usr/local/src
apt install autoconf libssl-dev zlib1g-dev libcurl4-openssl-dev tcl-dev gettext
wget https://github.com/git/git/archive/v2.22.1.tar.gz
tar zxvf v2.22.1.tar.gz
cd git-2.22.1/
make configure
./configure --prefix=/usr
make -j2
make install</code>

5. I recommend creating a new user to run your GhostBin code under:

<code class="language-shell hljs">adduser ghostbin</code>

6. You should also set a password on the new user account using <code>passwd ghostbin</code>
7. Login as your new user account and add the following to your <code>~/.bashrc</code>

<code class="language-bash hljs"><span class="hljs-built_in">export</span> GOPATH=<span class="hljs-variable">$HOME</span>/go</code>

8. Save and exit the file and run <code>source ~/.bashrc</code>
9. Next obtain the source code for QuickPaste (login as your new user first):

<code class="language-shell hljs">mkdir -p ~/go/src
cd $HOME/go/src
mkdir github.com
cd github.com
git clone https://github.com/nathanskywalker/quickpaste.git
cd spectre/</code>

To be continued...


