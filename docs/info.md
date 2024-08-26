<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

Badly probably.  

Use a positive edge detector on the clock and its compliment.  Or together those dectors to get 2 positive pulses per period or a 2x clock. 


## How to test

data source = in[1] ? lfsr : in[0]
clock source = in[2] ? clk : 2x clk

If you don't want to align in[0] to clock just use internal LFSR to make symbols. Check you get a new symbol on every clock edge. 

If you do want to use in[0] as data srouce:

Use in[2]=1 to find phase alignment of in[0] to FF0 in LFSR

From there use in[2]=0 and drive in[0] at alignment + 90 degrees out of phase with clock to try to grab data on every clock edge.  

## External hardware

None.
