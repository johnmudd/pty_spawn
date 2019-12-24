# pty_spawn
Use pty.spawn() as poor man's pexpect. Needed to automate tasks on thousands of very old Linux boxes.


Sample usage:

```
def main():
    p = Pty_spawn(["bash"])
    p.expect("$")
    p.sendline("date")
    p.expect(["2019", "2020"])
    p.sendline("echo 'hello'")
    p.expect("hello")
    p.sendline("exit")
    p.join()
```

Sample output:

```
mudd@ubuntu:~/misc$ date
Mon Dec 23 21:20:04 EST 2019
mudd@ubuntu:~/misc$ echo 'hello'
hello
mudd@ubuntu:~/misc$ exit
exit
```
