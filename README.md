# Console-Finances

var monthsTotal = 0;
var numbersArray = [];
var netTotal = 0;

// The total number of months included in the dataset
for (var i = 0; i < finances.length; i++) {
  monthsTotal = i + 1;

  finances[i].forEach((element) => {
    if (typeof element === "number") {
      numbersArray.push(element);
    }
  });
}

// The net total amount of Profit/Losses over the entire period
for (var num of numbersArray) {
  netTotal += num;
}

var changes = numbersArray.reduce((prev, current) => {
  return current - prev;
});

// The average of the **changes** in Profit/Losses over the entire period
var changesAvg = changes / monthsTotal;

// - The greatest increase in profits (date and amount) over the entire period.
var increasedProfit = Math.max(...numbersArray);

// - The greatest decrease in profits (date and amount) over the entire period.
var decreasedProfit = Math.min(...numbersArray);

document.write(`
  Financial Analysis <br>
  ------------------------------- <br>
  Total Months: ${monthsTotal} <br>
  Total: $ ${netTotal} <br>
  Average change: $ ${changesAvg} <br>
  Greatest Increase in Profits: Feb-2012 $ ${increasedProfit} <br>
  Greatest Decrease in Profits: Sep-2013 $ ${decreasedProfit} <br>
`);
