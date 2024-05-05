

function processData(input) {

    const lines = input.split('\n');
  
    const N = parseInt(lines[0]);
   
    const A = lines[1].split(' ').map(Number);

  
    function findThirdLargest(arr) {
        
        arr.sort((a, b) => a - b);
        
        return arr[arr.length - 3];
    }

   
    const result = findThirdLargest(A);

    
    console.log(result);
}


process.stdin.resume();
process.stdin.setEncoding("ascii");
let _input = "";
process.stdin.on("data", function (input) {
    _input += input;
});

process.stdin.on("end", function () {
   processData(_input);
});





-----------2

function isSorted(arr) {
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] < arr[i - 1]) {
            return false;
        }
    }
    return true;
}

function processData(input) {
    const arr = input.trim().split(' ').map(Number);
    const sorted = isSorted(arr);
    console.log(sorted);
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
    _input += input;
});



-----------3

function bankAccount(balance) {
    return {
        deposit: function(amount) {
            if (amount <= 0) {
                throw new Error("Deposit amount must be positive");
            }
            balance += amount;
            return balance;
        },
        withdraw: function(amount) {
            if (amount <= 0) {
                throw new Error("Withdrawal amount must be positive");
            }
            if (amount > balance) {
                throw new Error("Insufficient balance");
            }
            balance -= amount;
            return balance;
        },
        getBalance: function() {
            return balance;
        }
    };
}

function processData(input) {
    const balance = parseInt(input.trim());
    const account = bankAccount(balance);

    // Sample Input
    account.withdraw(1500);
    console.log(account.getBalance());
    account.deposit(500);
    console.log(account.getBalance());
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
    _input += input;
});

process.stdin.on("end", function () {
   processData(_input);
});

process.stdin.on("end", function () {
   processData(_input);
});

