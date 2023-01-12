const newspaperPrices = {
  TOI: {
    Monday: 3,
    Tuesday: 3,
    Wednesday: 3,
    Thursday: 3,
    Friday: 3,
    Saturday: 5,
    Sunday: 6,
  },
  Hindu: {
    Monday: 2.5,
    Tuesday: 2.5,
    Wednesday: 2.5,
    Thursday: 2.5,
    Friday: 2.5,
    Saturday: 4,
    Sunday: 4,
  },
  ET: {
    Monday: 4,
    Tuesday: 4,
    Wednesday: 4,
    Thursday: 4,
    Friday: 4,
    Saturday: 4,
    Sunday: 10,
  },
  BM: {
    Monday: 1.5,
    Tuesday: 1.5,
    Wednesday: 1.5,
    Thursday: 1.5,
    Friday: 1.5,
    Saturday: 1.5,
    Sunday: 1.5,
  },
  HT: {
    Monday: 2,
    Tuesday: 2,
    Wednesday: 2,
    Thursday: 2,
    Friday: 2,
    Saturday: 4,
    Sunday: 4,
  },
};

MySubscription = (amt) => {
  const m = [];
  for (const n1 of Object.keys(newspaperPrices)) {
    for (const n2 of Object.keys(newspaperPrices)) {
      const Totprice =
        Object.values(newspaperPrices[n1]).reduce(
          (x, y) => x + y,
          0
        ) +
        Object.values(newspaperPrices[n2]).reduce(
          (x, y) => x + y,
          0
        );
      if (Totprice <= amt && n1 !== n2) {
        m.push([n1, n2]);
      }
    }
  }

  return m;
}
console.log("Enter weekly expense:");
var inp = require("readline");

var n = inp.createInterface({
  input: process.stdin,
  output: process.stdout,
  terminal: false,
});
n.on("line", function (line) {
  console.log(MySubscription(line));
});
