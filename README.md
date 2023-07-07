* Google sheets script

* Background:

Google sheets has the ability to pull prices for the most popular crypto currencies, including Bitcoin, Ethereum, Litecoin, Cardano, and Binance Coin, but does not work with others such as Dogecoin etc.

You can still pull current crypto values for these coins into Google sheets but cannot create any decent ticket graphs etc without API's, costs & some effort (from my experience, YMMV)

There are a number of How to's on the web which show you how to set this up, the easiest is building your sheet and entering the following code in the corresponding cell for the crypto you are interested in:

I am using Dogecoin for this example, please check online for your crypto coin name & replace it as needed.

```=IMPORTDATA("https://cryptoprices.cc/DOGE/")```

* Creating something interesting:

I have zero script skills, but knew it should be easy enough to produce something, so what I have done is used ChatGPT to create this code for use in Google sheets.

* Steps
Note! For this example, the sheets are called "Sheet1" and "Sheet2", you can name them according to your needs

1) Open Google sheets, the first sheet should be called 'Sheet1'. Once you have your sheet setup, with your data, create a new sheet to record your crypto daily values. You should now have 2 sheets (Sheet1 and Sheet2)
2) Make a note of where your import value data is in Sheet1 (A1 etc)
3) Click on Extensions, then select "Apps Script'
4) On the new Window/Tab click the + button in the top right to create a new script. Select script.
5) Name your new script (I made mine relevant to my crypto - example "Daily Doge Value") then press enter to save
6) On the right side, delete everything in the code block and paste this code. It is a good idea to specify a name for the function especially if you want to use it for more than 1 currency. You can do this in the first line of the script (example, the existing script name is ```function recordDailyValue() {``` I named mine ```function recordDailyValueDoge() {``` and ```function recordDailyValueCro() {``` for example). Remember to modify the code to specify which cells you want to use. Rename the sheets if you want specific names.
7) Click the save icon (floppy disk)
8) Click Run to test, once completed, go to your Sheet2, to see if the data has been captured successfully.
9) Go to Triggers using the left menu (clock icon) and click the +Add Trigger icon at the bottom right.
10) Using the pop up window, you can setup a trigger to run your script, choose which function to run from the drop down (Whatever you called the function name in the script)
11) Select the event source from drop down (Time-driven) then adjust to what suits you.
12) Click save and that should be it.

That should be all, I have gone further and added a trend marker next to my values which checks the previous days value and compares it to the current value to see if it has gone up or down. This code can be inserted into the following cell (below the last value) - ```=IFS(B3>B2,"⇧",B3<B2,"⇩",TRUE,"-")``` I have used ASCII characters for up & down values, you can use whatever you want by replacing them in this function.

You can then create a graph to capture your daily movements that will create something interesting in the coming days / weeks/ months / years etc.

Enjoy and please feel free to use and change etc.

And special thanks to ChatGPT!!

