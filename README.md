# win-vm-setup
in short some of the nice way to get your newly created windows vm so that you wont need to interact with the "infirior browser" (you know who!)

### setup downloader

#### simple way
this is the simpelest one you can do... but sadly this is super slow, unless you are planning on downloading chrome installer since it's under 10mb but frankly i have no clue how to do it 
> there isn't any link that i can just copy paste from the site, only a button with as i see it an onclick listener... and frankly i ain't got time fo dat. and honestly if you really want chrome just download firefox then download chrome from it... 
 
```powershell
wget "https://download.mozilla.org/?product=firefox-latest&os=win64&lang=en-US" -OutFile ~\Downloads\firefox-installer-x64.exe
```

#### faster way
idk why this is not windows default wget instead (i guess its becs of the path param) but none the less this is the faster way

create the new object (i've tried not using the object thingy it doesn't work for some reason, if anything it's probably skill issue but i digress)  
```powershell
$wc = New-Object net.webclient
```

then use this format to download files

```powershell
$wc.Downloadfile("<url>", "<path>")
```

for example

##### firefox
```powershell
$wc.Downloadfile("https://download.mozilla.org/?product=firefox-latest&os=win64&lang=en-US", "~\Downloads\firefox-installer-x64.exe")
```
