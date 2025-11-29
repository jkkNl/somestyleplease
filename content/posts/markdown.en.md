+++
draft = true
title = 'Markdown Syntax'
date = 2020-07-07T00:00:00+08:00
+++

This is sample text intended to show[^1] a post with a large number of different elements.

# Sample Heading 1
## Sample Heading 2
### Sample Heading 3
#### Sample Heading 4
##### Sample Heading 5
###### Sample Heading 6

Lorem ipsum dolor sit amet. Sit dolor nihil aut blanditiis animi non dolores total cum consequatur nesciunt et quod exercitationem est dolorum aliquam. Ut quidem ullam vel Quis culpa ad repellendus corrupti qui delectus voluptatum sit eligendi assumenda.

## Lists

Dotted:

- One
- Two[^2]
- Three

Numbered:

1. Quisque arcu felis, laoreet vel accumsan sit amet, fermentum at nunc.
2. Sed massa quam, auctor in eros quis, porttitor tincidunt orci.
3. Nulla convallis id sapien ornare viverra.
4. Nam a est eget ligula pellentesque posuere.

## Quotations

You can place the quote in the appropriate block:
> If Ghandi had X, we would no longer have any authorities today.

## Line separating text

Mauris viverra dictum ultricies[^3]. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. **You can put some text inside the horizontal rule like so.**

---
{data-content = "there may be some text here"}

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. **Or you can just have an clean horizontal rule.**

---

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. Or you can just have an clean horizontal rule.

## Code
JavaScript formatting here:
```javascript
const ultimateTruth = 'this theme is the best!';
console.log(ultimateTruth);
```

C:
```c
#define UNICODE
#include <windows.h>

int main(int argc, char **argv) { 
int speed = 0, speed1 = 0, speed2 = 0; // 1-20 
printf("Set Mouse Speed ​​by Maverick\n"); 

SystemParametersInfo(SPI_GETMOUSESPEED, 0, &speed, 0); 
printf("Current speed: %2d\n", speed); 

if (argc == 1) return 0; 
if (argc >= 2) sscanf(argv[1], "%d", &speed1); 
if (argc >= 3) sscanf(argv[2], "%d", &speed2); 

if (argc == 2) // set speed to first value 
speed = speed1; 
else if (speed == speed1 || speed == speed2) // alternate 
speed = speed1 + speed2 - speed; 
else 
speed = speed1; // start with first value 

SystemParametersInfo(SPI_SETMOUSESPEED, 0, speed, 0); 
SystemParametersInfo(SPI_GETMOUSESPEED, 0, &speed, 0); 
printf("New speed: %2d\n", speed); 
return 0;
}
```
Python:
```python
# python test (sample from offlineimap)

class ExitNotifyThread(Thread): 
"""This class is designed to alert a "monitor" to the fact that a thread has 
exited and to provide for the ability for it to find out why.""" 
def run(self): 
global exitthreads, profiledir 
self.threadid = thread.get_ident() 
try: 
if not profiledir: # normal case 
Thread.run(self) 
else: 
try: 
import cProfile as profile 
except ImportError: 
import profiles 
prof = profile.Profile() 
try: 
prof = prof.runctx("Thread.run(self)", globals(), locals()) 
except SystemExit: 
pass 
prof.dump_stats( \ 
profiledir + "/" + str(self.threadid) + "_" + \ 
self.getName() + ".prof") 
except: 
self.setExitCause('EXCEPTION') 
if sys: 
self.setExitException(sys.exc_info()[1]) 
tb = traceback.format_exc() 
self.setExitStackTrace(tb) 
else: 
self.setExitCause('NORMAL') 
if not hasattr(self, 'exitmessage'): 
self.setExitMessage(None) 

if exitthreads: 
exitthreads.put(self, True)
```
Bash:

```bash
#!/bin/bash
cd $ROOT_DIR
DOT_FILES="lastpass weechat ssh Xauthority"
for dotfile in $DOT_FILES; to conform_link "$DATA_DIR/$dotfile" ".$dotfile"; done

# TODO: refactor with suffix variables (or common cron values)

case "$PLATFORM" in 
linux) 
#conform_link "$CONF_DIR/shell/zshenv" ".zshenv" 
crontab -l > $ROOT_DIR/tmp/crontab-conflict-arch 
cd $ROOT_DIR/$CONF_DIR/cron 
if [[ "$(diff ~/tmp/crontab-conflict-arch crontab-current-arch)" == "" 
]]; 
then # no difference with current backup 
logger "$LOG_PREFIX: crontab live settings match stored "\ 
"settings; no restore required" 
rm ~/tmp/crontab-conflict-arch 
else # current crontab settings in file do not match live settings 
crontab $ROOT_DIR/$CONF_DIR/cron/crontab-current-arch 
logger "$LOG_PREFIX: crontab stored settings conflict with "\ 
"live settings; stored settings restored. "\ 
"Previous settings recorded in ~/tmp/crontab-conflict-arch." 
fi 
;;
```

You can also mark a `line of code` in the text!

## Table:

| Tables | are | ok |
| ------------- |:-------------:| -----:|
| col 3 is | right-aligned | $1600 |
| col 2 is | centered | $12 |
| zebra stripes | are neat | $1 |

## Images

![Image](https://yavuzceliker.github.io/sample-images/image-1021.jpg)
Mountain view [^4].

## Categories and tags

[^1]: This is a footnote.
[^2]: Hey there!
[^3]: This is another footnote.
[^4]: This is a very, very, very long footnote. To see how this footnote is formatted. By the way, the image is from https://github.com/yavuzceliker/sample-images?tab=readme-ov-file.