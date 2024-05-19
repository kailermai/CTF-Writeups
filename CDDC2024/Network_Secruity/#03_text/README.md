# Challenge Name: <#03 text>

- Category: Network Security
- Points: <100>
- Solves: <160>

## Challenge Description

We captured a weird text file, can you open it?

## File Content

text.pcapng

## Solution

Opening the file in wireshark and following a tcp stream, we can change the stream to find the raw text file containing:

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas arcu leo, sodales nec lacus non, auctor suscipit nulla. Nunc in magna purus. Donec finibus auctor quam, in efficitur neque semper at. Quisque nulla lorem, dignissim pretium tortor sit amet, efficitur laoreet magna. Vestibulum consectetur vitae lorem id imperdiet. Suspendisse non interdum metus. Duis turpis metus, hendrerit id volutpat eget, lacinia id ex. Mauris posuere varius risus, at ornare elit tristique vel. Praesent lectus odio, rutrum cursus mi in, aliquam aliquam metus.

Maecenas sed metus et ipsum tincidunt porttitor. In eget posuere arcu, non malesuada diam. Mauris non vestibulum magna, sed euismod risus. Sed blandit imperdiet urna ac dapibus. Nullam porttitor tellus vitae lacus ornare bibendum. Vestibulum efficitur turpis nec dignissim mollis. Mauris mollis a felis eget lobortis. Phasellus pharetra viverra nibh, in vestibulum ex.

Maecenas ullamcorper augue a enim varius ullamcorper. Donec eu congue nibh. Proin euismod pretium rhoncus. Etiam velit leo, rhoncus at urna dapibus, pulvinar gravida quam. Mauris vitae magna vitae ante dignissim fringilla pulvinar sed libero. Ut sodales aliquet neque vel efficitur. Praesent ultrices justo in massa dapibus ultricies. Morbi auctor convallis diam quis interdum.

Etiam accumsan pulvinar nulla quis aliquet. Cras quis tempus nisl. Sed euismod aliquam enim, in semper mi facilisis eget. In laoreet risus at vehicula viverra. Integer porttitor pellentesque semper. Duis lacinia vehicula ex vel viverra. In vitae urna vitae quam scelerisque blandit. Ut a ante a ligula hendrerit porttitor. Suspendisse vestibulum diam in congue viverra. Nam pellentesque molestie felis, fermentum iaculis libero molestie eu. Ut porttitor condimentum finibus. Morbi at sollicitudin libero, et luctus magna. Vivamus scelerisque lacinia sem in feugiat. Nulla volutpat urna magna, at ornare mauris condimentum id.

Nullam vehicula ipsum quam, eget sollicitudin nisi scelerisque non. Quisque non mauris id lorem elementum imperdiet sit amet et velit. Integer augue felis, ultricies eget viverra sed, tincidunt at nulla. Integer maximus feugiat nunc, nec tempus nunc tincidunt sit amet. Morbi sollicitudin nulla ac eros accumsan, ac faucibus erat interdum. Nullam vitae consequat ex. Maecenas sit amet rutrum lectus. Proin sodales pellentesque suscipit. Aliquam erat volutpat.

Donec vitae pharetra augue. Aliquam feugiat, nulla eget ultricies vestibulum, nibh massa facilisis sem, a rutrum nibh nulla nec lorem. Nunc pulvinar pellentesque dictum. In eu feugiat ipsum. Curabitur bibendum, diam in suscipit tristique, orci lacus accumsan ante, eget pulvinar tortor purus nec erat. Morbi hendrerit nunc nisi, vel pulvinar nisl pretium ac. Morbi tristique, mauris at ultrices pellentesque, nibh metus vehicula mauris, id feugiat augue nulla et urna. Vivamus at aliquam lectus. Nam maximus lectus velit, ut pellentesque sem feugiat sed.

Quisque dapibus sem ut urna varius cursus. Vestibulum ac facilisis libero. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Suspendisse ullamcorper fermentum risus eu dapibus. Integer hendrerit nisi leo, euismod rutrum lorem bibendum imperdiet. Quisque finibus risus sed facilisis facilisis. Aliquam rhoncus elit at tristique dapibus. Cras urna magna, vulputate sed vulputate et, lobortis ut felis. Morbi bibendum laoreet nibh nec pulvinar. Aenean a aliquet felis, ut efficitur mauris. Donec euismod lacus at semper vehicula. Suspendisse eget leo sed purus semper imperdiet ac vitae massa. Cras congue urna eget semper hendrerit. Curabitur eget mauris imperdiet, iaculis metus vel, lobortis justo. Curabitur commodo varius felis volutpat maximus. Nam dui ipsum, consequat ac nibh sed, volutpat sagittis justo.

Vestibulum non finibus turpis. Aenean eget fringilla ante. In tincidunt faucibus diam, in viverra lectus hendrerit sed. Proin facilisis gravida nulla vitae finibus. Vivamus tristique dui nec eros consequat varius. Curabitur fermentum, sapien a rutrum aliquam, lectus nunc tempor eros, eget commodo enim tortor at tortor. Nam rhoncus ac leo at placerat. Nulla dictum ullamcorper felis, sed ullamcorper ipsum.

Integer sed odio sit amet massa rutrum accumsan non ac enim. Nam a nibh nisl. Mauris ornare faucibus nibh eget bibendum. Nulla facilisi. Etiam scelerisque quis ex vel commodo. Nulla eu venenatis nisl. Sed auctor porta leo. Maecenas nec felis faucibus, bibendum elit et, placerat nunc. Pellentesque eget nunc mauris. Maecenas feugiat lectus orci, non dictum nibh pulvinar non. Phasellus eu accumsan felis. Sed sodales, urna nec ornare placerat, quam metus vulputate ante, id facilisis massa tellus at diam. Quisque enim urna, imperdiet nec tincidunt eget, ultricies non dolor. Phasellus commodo ex massa, eu consectetur est mollis ut. Nulla blandit dapibus pharetra. Proin lacinia, est nec gravida pharetra, lacus nisl condimentum quam, quis mollis eros metus ac purus.

In purus sem, suscipit nec lorem sed, consequat lacinia sapien. In tempor tincidunt ex nec efficitur. Phasellus ante quam, dignissim in quam non, placerat porttitor massa. Curabitur nec risus dignissim, consectetur dolor at, fermentum turpis. Morbi et urna velit. Curabitur fringilla, velit et dapibus ullamcorper, risus odio dapibus nibh, et efficitur massa magna euismod erat. Ut ipsum ipsum, porta faucibus ex eu, sodales feugiat mi. Vestibulum tincidunt massa sed lacinia eleifend. Etiam facilisis efficitur turpis, in ultricies lorem iaculis eu. Sed hendrerit, urna eget interdum pellentesque, purus diam commodo lectus, vel ultrices arcu nulla pellentesque justo. Pellentesque ultrices sagittis lobortis.

Phasellus placerat nisi sapien, nec vulputate ligula varius ut. Suspendisse potenti. Maecenas placerat leo quam, at pulvinar mauris euismod congue. Sed vehicula in diam eu blandit. Sed consectetur, nisi eget rhoncus eleifend, libero nulla finibus dui, nec sodales orci nunc ut dolor. Proin ultricies lacinia orci non convallis. Etiam vehicula convallis neque, id dignissim nulla facilisis at. Suspendisse augue dolor, imperdiet quis ipsum sed, iaculis laoreet nunc. Morbi purus elit, dictum ut eros in, commodo tristique enim. In vitae ex aliquet, consequat leo quis, vehicula ipsum. Nam quam elit, eleifend sed justo vel, fermentum fermentum urna. Mauris magna lacus, cursus quis placerat ut, sagittis ac nisi. Cras posuere dolor eget volutpat cursus. Suspendisse tincidunt nisi lectus, vitae aliquam odio faucibus non. Sed eget malesuada turpis, quis malesuada odio. Aenean ac rhoncus odio, eget maximus purus.

Mauris eleifend lacus fermentum lacus varius feugiat. Curabitur id velit nulla. Aliquam gravida libero urna, sit amet condimentum velit pulvinar nec. Phasellus a felis nec quam ultrices rhoncus eget at ligula. Sed tincidunt massa mi, id aliquet ipsum fermentum sed. Aenean odio urna, mattis ac est vel, sodales tincidunt metus. Fusce congue velit nisi, sit amet molestie tellus hendrerit ac. Vivamus a metus eu arcu dapibus luctus. Donec quis nisl tortor. Integer convallis sem quis tortor faucibus blandit. Aliquam ultricies commodo pellentesque. Fusce leo eros, efficitur id dapibus quis, aliquet id quam. Phasellus pulvinar, est ut hendrerit posuere, nisl metus euismod metus, id gravida justo elit sit amet purus.

Nunc id libero nunc. Etiam id elit quam. Donec ornare facilisis ligula, eget eleifend ligula iaculis vel. Ut accumsan convallis consectetur. Nulla vitae eleifend eros. Cras malesuada orci quis rhoncus gravida. Curabitur sed lacus egestas, sodales augue suscipit, placerat mauris. Donec porttitor, massa ac lacinia vulputate, quam eros sagittis nisi, sed placerat mauris erat et ex. Morbi quis maximus eros. Nam consectetur quam vel dui semper sagittis. Fusce sit amet justo dapibus, condimentum metus at, euismod nisi. Suspendisse ullamcorper sem id ultricies rutrum. Donec semper felis orci, in iaculis tellus fermentum et. Praesent aliquam diam vel egestas lobortis. Quisque sollicitudin elit nec erat fringilla semper.

Vestibulum dapibus ornare turpis gravida faucibus. Vestibulum ut neque in magna sollicitudin maximus. Quisque aliquet lacus nec consectetur maximus. Nunc eu odio mollis ipsum tempus viverra commodo sed massa. Maecenas mollis fermentum sapien, at volutpat lorem auctor ut. Nullam porta elementum leo, at eleifend mi porta in. Sed eu pulvinar nulla. Fusce in bibendum lacus, sit amet auctor felis. Nullam viverra est at felis aliquet, in ornare metus semper. Nunc ullamcorper ut ex ac porttitor.

Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aliquam placerat risus sed nisi pulvinar, vel auctor ante egestas. Nullam ac finibus magna, pellentesque tristique justo. Suspendisse at sollicitudin tellus. Aenean hendrerit tristique feugiat. Vivamus malesuada laoreet tortor. Integer sed ipsum eleifend lorem accumsan scelerisque. In accumsan vulputate eros, eget fermentum lacus volutpat id.

aHR0cHM6Ly9kb2NzLmdvb2dsZS5jb20vZG9jdW1lbnQvZC8xTEJHU284MWZ3ZDNEOUlxa2x1MFV2S0dMbUVTVzdhTXV6UWRJYlk2UGlhWS9lZGl0P3VzcD1zaGFyaW5n

This is the end, aka fin.
```

We see a weird text at the bottom that isn't part of Lorum Ipsum, putting it into a decoded gets us a link to a google docs. 

![Screenshot of the challenge](/Images/networksecurity03text.png)

Highlighting the entire document gets us the flag.

## Flag

CDDC2024{foLL0w_tHe_n3tw0Rk_trA1L}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)
