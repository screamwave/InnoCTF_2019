# Hex64

When I first started doing this challenge, I tried to do it by hand.

Decoding the base64 text and putting the data to a file as bytes but after doing a few times, I realized its pretty nested so I wrote the script below.

```
#!/usr/bin/env python2

import base64
import binascii

def write_to_file(data, out_path):
    print('Writing to {}'.format(out_path))
    try:
        open(out_path, 'wb').write(data)
    except:
        print('Something went wrong D:')
        exit()
    return out_path

def read_ascii_from_file(in_path):
    print('Reading from {}'.format(in_path))
    data = open(in_path, 'r').read()
    try:
        return data.decode('hex')
    except:
        try:
            return base64.b64decode(data)
        except:
            print('We got the flag! Or not...?')
            exit()

original_file = base64.b64decode(open('Hex64','r').read())

counter = 1
hex_file_holder = ""

while True:
    base_filename = 'Hex64_'

    print(hex_file_holder)
    if hex_file_holder == "":
        hex_file_holder = write_to_file(original_file, base_filename+str(counter))
    else:
        hex_file_holder = write_to_file(read_ascii_from_file(hex_file_holder), base_filename+str(counter))
    counter += 1

```

While the solution above isn't very elegant but it works.

```
InnoCTF{PpC_17_pl34se}
```

