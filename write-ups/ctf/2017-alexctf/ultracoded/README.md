First let's see what's in the file by running cat zero_one:

ZERO ONE ZERO ZERO ONE ONE ZERO ZERO ZERO ONE ONE ZERO ONE ZERO ZERO ONE ZERO ZERO ONE ONE ZERO ZERO ZERO ZERO ZERO ONE ONE ZERO ZERO ONE ONE ONE ZERO ONE ZERO ZERO ONE ONE ZERO ZERO ZERO ONE ONE ZERO ONE ZERO ZERO ONE ZERO ZERO ONE ONE

Ok so that's probably binary. But strings aren't helpful, so we need to convert that into 0's and
1's. So I developed a very simple python script to get my binary code.

  1 f = open('zero_one', 'r')
  2 f2 = f.read()
  3 
  4 d = f2.replace("ZERO", "0")
  5 d = d.replace("ONE", "1")
  6 d = d.replace(" ", "")
  7 print d

With the binary in hands, we can convert it to ASCII and get the string

Li0gLi0uLiAuIC0uLi0gLS4tLiAtIC4uLS4gLSAuLi4uIC4tLS0tIC4uLi4uIC0tLSAuLS0tLSAuLi4gLS0tIC4uLi4uIC4uLSAuLS0uIC4uLi0tIC4tLiAtLS0gLi4uLi4gLiAtLi0uIC4tLiAuLi4tLSAtIC0tLSAtIC0uLi0gLQ==

I can be wrong, but that's probably base64 code. So decoding it we get the string

.- .-.. . -..- -.-. - ..-. - .... .---- ..... --- .---- ... --- ..... ..- .--. ...-- .-. --- ..... . -.-. .-. ...-- - --- - -..- -

Wow, nice morse code bro. Fortunately we can decode it to text and get the string

ALEXCTFTH15O1SO5UP3RO5ECR3TOTXT

Now we just do some changes and get the right flag :)
