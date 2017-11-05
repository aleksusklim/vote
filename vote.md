<h1>BASIC (zx spectrum), &lt;30 bytes</h1>

*All right, for those who wanna `golf` and see my most BASIC program – just read from here, but if VOTING is what take you here, like me – scroll down for a bit.*

<hr>

Well… I thought that VOTING is more important than anything, but sadly moderators (*and community*) still think that the most important thing is GOLFING. So, I’m not disappointed, and made for you a really small line of `BASIC` code that works on Sinclair ZX Spectrum, my very first personal computer and my first programming language!

Here is the program:

`1 PRINT "{BRIGHT 1}{INK 2}I {INK 1}V{INK 2}o{INK 1}t{INK 2}e{INK 1}d"`

But it’s not a real spectrum code, it is just a text that should be feed to <a href="http://www.worldofspectrum.org/utilities.html#other">BAS2TAP compiler</a>.

70 ASCII-chars (including the end of line).

Actually, it produces a .TAP file. To easily run it, I give you the encoded version:

`data:text/cmd;base64,EwAAAFZPVEUgICAgICAdAAAAHQAIHwD/AAEZAPUiEwEQAkkgEAFWEAJvEAF0EAJlEAFkIg0r`

This URI is 93 characters in Base64, but the real TAP file size is 54 bytes.

Visit <a href="http://jsspeccy.zxdemo.org/">this online emulator</a> and press “Open file” (4-th button, «folder»), flip “Spectrum 128K” to “Spectrum 48K”, paste that "data:text…" to “Load from web:” field and finally hit “Open URL”!

But my program is even smaller. You see, Spectrum uses one byte for language <a href="https://en.wikipedia.org/wiki/ZX_Spectrum_character_set">keywords and control codes</a>.

So `PRINT` (and spaces around it) is just one “char” from ZX’s point of view. If I will not count line number “1” (piece of code could be executed directly) and final ENTER, then program dump looks like this:
<!-- language-all: lang-none -->

    Offset   |  0  1  2  3  4  5  6  7   8  9 10 11 12 13 14 15 |
    ---------+--------------------------------------------------+-----------------
    00000000 | F5 22 13 01 10 02 49 20  10 01 56 10 02 6F 10 01 | х"....I ..V..o..
    00000016 | 74 10 02 65 10 01 64 22                          | t..e..d"

**24 bytes**

Color codes are represented as two byte sequences. But they could be written as one logical character from the keyboard!

Since we don’t need to restore colors after line, my logical length is this: “1” as line number; keyword “PRINT” (typed with only one keypress); quote char. Then comes BRIGHT mode (to make background pure white) and BLUE ink. Then type all letters with according color (can switch to RED directly). And a final quote. That way, I got 18.

Also we can count actual keystrokes that are needed to write this program to Spectrum! <a href="http://torinak.com/qaop">Go here.</a>

`Ctrl` key stand for SYMBOL SHIFT and `Shift` stand for CAPS SHIFT. The combination “Ctrl+Shift” will put the cursor in "E" mode and back, so don’t hold it for long.

To type my golfing, press this key sequence:

<kbd>1</kbd> <kbd>P</kbd> <kbd>CTRL+P</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>9</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+2</kbd> <kbd>SHIFT+I</kbd> <kbd>SPACE</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+1</kbd> <kbd>SHIFT+V</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+2</kbd> <kbd>O</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+1</kbd> <kbd>T</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+2</kbd> <kbd>E</kbd> <kbd>CTRL+SHIFT</kbd> <kbd>SHIFT+1</kbd> <kbd>D</kbd> <kbd>CTRL+P</kbd> <kbd>ENTER</kbd> <kbd>R</kbd> <kbd>ENTER</kbd>

We have as much as 28 keystrokes!

![0 OK, 1:1](https://i.stack.imgur.com/HxkIK.png "0 OK, 1:1")

<hr>
<h1>VOTING!</h1>

Yesterday (two days ago, actually…) was December 4th, 2016, <a href="https://en.wikipedia.org/wiki/Uzbekistani_presidential_election,_2016">Election Day</a> in the Republic of Uzbekistan.

Since I am an Uzbekistan citizen eligible to vote, then I went out and voted before answering this challenge.

Than I returned home and wrote this absolutely regular C code, that has nothing special:
<!-- language-all: lang-none -->

    ///\\ http://codegolf.stackexchange.com/questions/98968 //\\\
    program{:} GoOutAndVote;{&call:vote - %~nx0 & goto:eof
    /*}{$apptype console} uses windows;
    var c,i,k,r,l:integer;(*/
    #include<windows.h>//#echo off
    #include<stdio.h>//#cls
    typedef struct{int z;} Z;
    #define chr//#call:vote f 0 113 202 140 255 0
    #define dec//#call:vote 8 0 0 0
    #define then//#call:vote a 0 255 192 192 255 0 127 72 48
    #define And &//#call:vote f 0 62 65 62
    #define div / //#call:vote a 0 127 64 64
    #define Or |1|//#call:vote f 0 62 65 62 0
    #define cardinal//#call:vote a 3 62 96 63 0
    #define inc(a) a++//#call:vote f 62 65 62 0
    #define p(n,v) n=v//#call:vote a 62 97 65 0
    #define repeat do{//#call:vote f 62 65 62 0
    #define Not(c) (!c)//#call:vote a 127 89 103 0
    #define write(t) putc(t,stdout)//#call:vote f 63 68 68 63
    #define begin int main(){//#call:vote a 0 3 62 96 63 0
    #define until(x) }while(!(x))//#call:vote - -
    #define end }int z(Z z){z//#goto:eof
    int c,i,k,r,l,a[]={13,25,5,-15,-1,-100,0};/*)
    var a:array[0..15] of integer=
    (24,9,-78,47,39,-7,11,-90,34,35,13,-14,5,4,-109,0);
    procedure p(var n:Integer;v:Integer);begin n:=v;end;//*/
    begin p(i,0);p(c,0);p(r,73);p(k,249);p(l,6);
    dec(c,1);dec(r,-4);repeat
    dec(l,-(c And 2)div 2);
    if((i<3)Or(i>3)And(i<12)Or(i>12))then inc(c);
    SetConsoleTextAttribute(
    GetStdHandle(cardinal(-11)),k+(c And 1)*3);
    write(chr(r));if Not(i>0)then write(' ');
    if Not(c>0)then write(chr(8));
    p(r,r+a[i]);if Not(r>0)then p(k,4);
    inc(i);until(i-l>0);end. z=0;}/*
    :vote
    if %1==- set d="%temp%\GoOutAndVote\"
    if %1==- rmdir /s /q %d% 1>nul 2>nul
    if "%2"=="-" goto:eof
    if %1==- mkdir %d% 1>nul 2>nul
    if %1==- for /f "tokens=2 delims=#" %%i in (%2) do %%i
    pushd %d% & set f=%1
    :shift
    shift & set a=%2
    if "%1"=="" popd & goto :eof
    set /a i=8 & set s=!
    :goto
    set /a "b=a&1,a>>=1" & set c=#
    if %b%==0 set c=-
    set /a i-=1 & set s=%s%%c%
    if not %i%==0 goto:goto
    echo. >%s%
    findstr /v /a:0%f% ! !*
    del %s% & goto:shift
    \\\*alekuskslim*///

I followed this unofficial rule, `vowels are red, consonants are blue`. This thing should compile with BCC32 or, maybe MS Visual Studio (VC 2008 tested). Also, <a href="http://www.onlinecompiler.net/ccplusplus">online C compiler</a> did the work, just make sure to target Windows OS.

But you know what? Here, “I Voted” really means nothing, because it must be in Uzbek. So, let’s take a chance and compile it under Delphi with DCC32:

![I Voted / Men Ovoz Berdim](https://i.stack.imgur.com/pPyeV.png "I Voted / Men Ovoz Berdim")

Great, isn’t it? (again, possible <a href="http://www.onlinecompiler.net/pascal">online</a>; but, just like previous, it will not show the output, encourages you to download and test .exe manually instead)

…not as quite as it can be. Thing is, I’m Russian, and that “Men Ovoz Berdim” (like «I gave my vote») does not fully express my exciteness about it. Wait, this code little reminds… a WinCmd Batch script!? Why, let’s try this too:

![Я Проголосовал](https://i.stack.imgur.com/z5rGx.png "Я Проголосовал")

YAY! That’s what I call the VOTE. “Я Проголосовал” (read as «ya progolosoval») is printed vertically as kinda ACSII art, in white+green – which also are colors from <a href="https://en.wikipedia.org/wiki/Flag_of_Uzbekistan">Uzbekistan’s Flag</a> (background is black intentional: I thought, enough of negative!)

OK, if someone is interested, I can explain how it works. This polyglot is based on:
<ul>
<li><code>//……\</code>  C-comment, which makes next line to be a comment too. Delphi will see only first line commented. Moreover, it will happily ignore everything after the final <code>end.</code></li>
<li><code>{…}</code> is multiline comment in Delphi, but <code>/*…*/</code> in C. Also, <code>(*…*)</code> – this is a Delphi comment too, easy allowing ninjas with <code>…(*/…/*)…(*/…</code>.</li>
<li>Batch will ignore errors with wrong filenames and everything, but execute command after `&`. It can jump to a label located at the end of file and it is possible to read and parse the source code as strings to execute only some parts of it.</li>
</ul>

If I replace and shrink C code comments to "_", the program will look like this:

<!-- language-all: lang-c -->

    //_\
    _
    /*_
    _*/
    #include<windows.h>//_
    #include<stdio.h>//_
    typedef struct{int z;} Z;
    #define chr//_
    #define dec//_
    #define then//_
    #define And &//_
    #define div / //_
    #define Or |1|//_
    #define cardinal//_
    #define inc(a) a++//_
    #define p(n,v) n=v//_
    #define repeat do{//_
    #define Not(c) (!c)//_
    #define write(t) putc(t,stdout)//_
    #define begin int main(){//_
    #define until(x) }while(!(x))//_
    #define end }int z(Z z){z//_
    int c,i,k,r,l,a[]={13,25,5,-15,-1,-100,0};/*_
    _*/
    begin p(i,0);p(c,0);p(r,73);p(k,249);p(l,6);
    dec(c,1);dec(r,-4);repeat
    dec(l,-(c And 2)div 2);
    if((i<3)Or(i>3)And(i<12)Or(i>12))then inc(c);
    SetConsoleTextAttribute(
    GetStdHandle(cardinal(-11)),k+(c And 1)*3);
    write(chr(r));if Not(i>0)then write(' ');
    if Not(c>0)then write(chr(8));
    p(r,r+a[i]);if Not(r>0)then p(k,4);
    inc(i);until(i-l>0);end. z=0;}/*
    _
    _*///_

After #define substitution we got:

<!-- language-all: lang-c -->

    #include<windows.h>
    #include<stdio.h>
    typedef struct{int z;} Z;
    int c,i,k,r,l,a[]={13,25,5,-15,-1,-100,0};
    int main(){ i=0;c=0;r=73;k=249;l=6;
    do{
    if((i<3)|1|(i>3)&(i<12)|1|(i>12))c++;
    SetConsoleTextAttribute(
    GetStdHandle(-11),k+(c&1)*3);
    putc(r,stdout);if(!i>0)putc(' ',stdout);
    if(!c>0)putc(8,stdout);
    r=r+a[i];if(!r>0)k=4;
    i++;}while(!(i-l>0));}int z(Z z){z . z=0;}

My a[] array is a difference between code points for characters in target string. First condition (and Char#8) is for Delphi and always evaluates to true. Param to SetConsoleTextAttribute is flipped after every iteration, but immediately following the first letter one space is printed. After last iteration the sum of array will be zero, and color is changed back to black+gray before returning control out of the program. Last sleepy “ZZZ” hacking is there to get rid of the dot after Delphi’s "end.".

Now, Delphi sees this:

<!-- language-all: lang-pascal -->

    //_
    program{:} GoOutAndVote;{_
    _}{$apptype console} uses windows;
    var c,i,k,r,l:integer;(*_
    _*)
    var a:array[0..15] of integer=
    (24,9,-78,47,39,-7,11,-90,34,35,13,-14,5,4,-109,0);
    procedure p(var n:Integer;v:Integer);begin n:=v;end;//_
    begin p(i,0);p(c,0);p(r,73);p(k,249);p(l,6);
    dec(c,1);dec(r,-4);repeat
    dec(l,-(c And 2)div 2);
    if((i<3)Or(i>3)And(i<12)Or(i>12))then inc(c);
    SetConsoleTextAttribute(
    GetStdHandle(cardinal(-11)),k+(c And 1)*3);
    write(chr(r));if Not(i>0)then write(' ');
    if Not(c>0)then write(chr(8));
    p(r,r+a[i]);if Not(r>0)then p(k,4);
    inc(i);until(i-l>0);end. _

"{:}" after "program" parsed as comment, but potentially needed for Batch. Here I have another a:array of char-code differences. Function p(name,value) is to do name:=value, since I couldn’t figure it out how to make C to eat all those `:=` ("#define :" didn’t work out). Algorithm is the same, but here all spaces are hardcoded as characters (I mean, numbers), and two color changes at vowels `_O` («red» space + red O) and consonants `rd` are combined in that first long condition. Length "l" is calculated somewhat tricky… Actually I just changed and compiled stuff at random until it worked! (Hey, isn’t my chr(8) there only for sake of cancelling the space that is printed just a line ago!? Oh, I might do that better..)

All right, here comes batch!

Firstly, it tries to run `///\\.exe`, but it’s impossible. Then it find out that `program{:}` is a forbidden name for an application, but sees `&call:vote - %~nx0 & goto:eof` and transfers control to ":vote" label with %1 = "-", %2 = "(name of current script)". Wow, %~snx0 might be better… anyway, DON’T EVEN TRY to execute this file with spaces in the name, or path that has something except letters and digits…

Then, beginning from :vote there is just pure batch code:
<!-- language-all: lang-default-->

    if %1==- set d="%temp%\GoOutAndVote\"
    if %1==- rmdir /s /q %d% 1>nul 2>nul
    if "%2"=="-" goto:eof
    if %1==- mkdir %d% 1>nul 2>nul
    if %1==- for /f "tokens=2 delims=#" %%i in (%2) do %%i
    pushd %d% & set f=%1
    :shift
    shift & set a=%2
    if "%1"=="" popd & goto :eof
    set /a i=8 & set s=!
    :goto
    set /a "b=a&1,a>>=1" & set c=#
    if %b%==0 set c=-
    set /a i-=1 & set s=%s%%c%
    if not %i%==0 goto:goto
    echo. >%s%
    findstr /v /a:0%f% ! !*
    del %s% & goto:shift

It needs empty temp directory to create files with special name, so to make it sure, I must recursively delete stuff… But don’t worry, it will not touch anything that does not belong to it. Main script loop is the parsing of script itself with FOR loop. It looks for strings with two "#" (it C’s defines and includes) and executes everything past those. So there are several other calls to voting:
<!-- language-all: lang-default -->

    echo off
    cls
    call:vote f 0 113 202 140 255 0
    call:vote 8 0 0 0
    call:vote a 0 255 192 192 255 0 127 72 48
    call:vote f 0 62 65 62
    call:vote a 0 127 64 64
    call:vote f 0 62 65 62 0
    call:vote a 3 62 96 63 0
    call:vote f 62 65 62 0
    call:vote a 62 97 65 0
    call:vote f 62 65 62 0
    call:vote a 127 89 103 0
    call:vote f 63 68 68 63
    call:vote a 0 3 62 96 63 0
    call:vote - -
    goto:eof

Firstly, we disable echoing and clear screen (there were several error messages!) and then execute a bunch of commands. Last one "- -" is to delete temp folder and exit script. But others have in %1 color code, and next arguments – bytes that represent numerical rows. Each row is a byte and consists of eight "-" (zero bit) or "#" (one bit). All rows will be printed with the same color, allowing grouping. Previous code has a bit-parser that converts numbers to printable rows strings. Then I put that string as a name of new file, and point `findstr.exe` to it, which will print that name in chosen color (with ":" at the end).

Well. The last thing I can do is to give you the full build script. With all required compilers and stuff… If you really want to execute it yourself and make sure that everything will work perfectly, here is my challenge! Download <a href="http://imgur.com/a/tqiwY">these three</a> small files:

<ul>
<li><a href="http://i.imgur.com/jNJTR8X.png">vote.part01.rar.png</a></li>
<li><a href="http://i.imgur.com/PZuYvBi.png">vote.part02.rar.png </a></li>
<li><a href="http://i.imgur.com/ce2apPa.png">vote.part03.rar.png </a></li>
</ul>

They are just regular archives, again nothing unusual. But, to make it more rar-compatible, you should open each one in MSPaint and save as 24-bit Bitmap. Then rename all three as I showed (`.part0*.rar`) and unpack the first one with WinRar, do not use spaces and other weird characters in file/directory names. I believe, soon you will have BUILD.CMD that makes everything, just run it!

Oh, hope I didn’t mess up anything. Also successfully edited this answer after I got enough reputation, thank you guys!