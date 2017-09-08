# csv-diff
Examples on how to diff csv files.

In the directory `exmaples`, there are two files `file-newer.csv` and `file-older.csv`.

They are about 35,000 lines each and represent two different versions of a product pricelist.

## Basic diff

You can do a basic diff of these two files like this:

```bash
diff examples/file-newer.csv examples/file-older.csv
```

Which will produce about 4,000 lines like this:

```bash
> "VALL","VALV8186","Crystal Hdle",24.00,"0.5000 ",12.00,0.00,0.00,0.00,0.00,0.00,12.00
34628c34740
< "WATE","WATBV107D-R","Bonnet (6 Pack)",30.93,"0.8000 ",24.74,0.00,0.00,0.00,0.00,0.00,24.74
---
> "WATE","WATBV107B-R","Pure Water Binnet (6)",32.10,"0.8000 ",25.68,0.00,0.00,0.00,0.00,0.00,25.68
34757a34870,34871
> "ZURC","ZUR59454001","Red Hdle Index",0.45,"0.6000 ",0.27,0.00,0.00,0.00,0.00,0.00,0.27
> "ZURC","ZUR59454002","Blue Index Btn",0.45,"0.6000 ",0.27,0.00,0.00,0.00,0.00,0.00,0.27
34763a34878,34879
> "ZURC","ZUR62301001","1/2 Vac Breaker Repair Kit",12.35,"0.6000 ",7.41,0.00,0.00,0.00,0.00,0.00,7.41
> "ZURC","ZUR7000-11D","Retainer Screw (1)",2.90,"0.6000 ",1.74,0.00,0.00,0.00,0.00,0.00,1.74
34769a34886,34887
> "ZURC","ZUR7600-LH","Metal Hdle w/Index & Screw",26.85,"0.6000 ",16.11,0.00,0.00,0.00,0.00,0.00,16.11
> "ZURC","ZURA26915","Aquasense Faucet",618.20,"0.6000 ",370.92,0.00,0.00,0.00,0.00,0.00,370.92
34795a34914
> "ZURC","ZURG66620","10"" Gooseneck Spout",105.90,"0.6000 ",63.54,0.00,0.00,0.00,0.00,0.00,63.54
34797a34917,34919
> "ZURC","ZURP1310SCREW","Screw",5.00,"0.6000 ",3.00,0.00,0.00,0.00,0.00,0.00,3.00
> "ZURC","ZURP1310SEAT","Seat",17.00,"0.6000 ",10.20,0.00,0.00,0.00,0.00,0.00,10.20
> "ZURC","ZURP1310WASHER","Washer",5.00,"0.6000 ",3.00,0.00,0.00,0.00,0.00,0.00,3.00
34802a34925
> "ZURC","ZURP6900-B-L","Solenoid",370.05,"0.6000 ",222.03,0.00,0.00,0.00,0.00,0.00,222.03
34821a34945
> "ZURC","ZURZ1996SFHDLRK","Handle Assy",10.50,"0.6000 ",6.30,0.00,0.00,0.00,0.00,0.00,6.30
```

The first character `>`/`<` indicate that the line is present in one file but not the other.

### Saving our results

It's not super useful to print 4,000 lines of text to your console, so you should redirect the output to a file.  That looks like this:
```bash
diff examples/file-newer.csv examples/file-older.csv > examples/differences.txt
```

The additional part ` > examples/differences.txt` tells the console to send the text that would have gone to the screen to a file instead.  This way you can review the results in a text editor.

