// ============================================
// PROBLEM 1: Array Filtering and Mapping
// ============================================

function filterAndMapNames() {
  const people = [
    { name: "John", age: 30, gender: "male" },
    { name: "Sarah", age: 25, gender: "female" },
    { name: "Mike", age: 35, gender: "male" },
    { name: "Emily", age: 28, gender: "female" },
    { name: "David", age: 32, gender: "male" }
  ];

  // Filter out females, map to names
  const maleNames = people
    .filter(person => person.gender !== "female")
    .map(person => person.name);

  console.log("Problem 1 - Male Names:", maleNames);
  return maleNames;
}

// ============================================
// PROBLEM 2: Object Manipulation
// ============================================

function extractBookTitles() {
  const books = [
    { title: "To Kill a Mockingbird", author: "Harper Lee", year: 1960 },
    { title: "1984", author: "George Orwell", year: 1949 },
    { title: "The Great Gatsby", author: "F. Scott Fitzgerald", year: 1925 },
    { title: "Pride and Prejudice", author: "Jane Austen", year: 1813 }
  ];

  // Extract only titles
  const titles = books.map(book => book.title);

  console.log("Problem 2 - Book Titles:", titles);
  return titles;
}

// ============================================
// PROBLEM 3: Function Composition
// ============================================

function functionComposition() {
  // Three individual functions
  const square = num => num * num;
  const double = num => num * 2;
  const addFive = num => num + 5;

  // Compose functions: square -> double -> add 5
  const compose = (num) => {
    return addFive(double(square(num)));
  };

  // Alternative using function composition pattern
  const composeChain = (value) => {
    let result = value;
    result = square(result);
    result = double(result);
    result = addFive(result);
    return result;
  };

  // Test: square(3)=9, double(9)=18, addFive(18)=23
  const testNumber = 3;
  const result = compose(testNumber);

  console.log(`Problem 3 - Compose(${testNumber}):`, result);
  return result;
}

// ============================================
// PROBLEM 4: Sorting Objects
// ============================================

function sortCarsByYear() {
  const cars = [
    { make: "Toyota", model: "Camry", year: 2020 },
    { make: "Honda", model: "Civic", year: 2015 },
    { make: "BMW", model: "X5", year: 2022 },
    { make: "Ford", model: "Mustang", year: 2018 },
    { make: "Audi", model: "A4", year: 2019 }
  ];

  // Sort by year in ascending order
  const sortedCars = cars.sort((a, b) => a.year - b.year);

  console.log("Problem 4 - Cars Sorted by Year:");
  console.table(sortedCars);
  return sortedCars;
}

// ============================================
// PROBLEM 5: Find and Modify
// ============================================

function findAndModifyPerson() {
  const people = [
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 },
    { name: "Charlie", age: 35 },
    { name: "Diana", age: 28 }
  ];

  // Function to find and modify
  const findAndUpdateAge = (array, name, newAge) => {
    const person = array.find(p => p.name === name);
    if (person) {
      person.age = newAge;
    }
    return array;
  };

  // Find "Bob" and change age to 31
  const updated = findAndUpdateAge(people, "Bob", 31);

  console.log("Problem 5 - Updated Array:");
  console.table(updated);
  return updated;
}

// ============================================
// PROBLEM 6: Array Reduction
// ============================================

function sumEvenNumbers() {
  const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

  // Use reduce to sum only even numbers
  const sum = numbers.reduce((acc, num) => {
    return num % 2 === 0 ? acc + num : acc;
  }, 0);

  console.log("Problem 6 - Sum of Even Numbers:", sum);
  return sum;
}

// ============================================
// PROBLEM 7: Leap Year Checker
// ============================================

function isLeapYear(year) {
  // A year is a leap year if:
  // 1. Divisible by 4 AND
  // 2. NOT divisible by 100 OR divisible by 400

  const leap = (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);

  console.log(`Problem 7 - Is ${year} a leap year?`, leap);
  return leap;
}

// ============================================
// PROBLEM 8: Unique Values
// ============================================

function filterUniqueNumbers() {
  const numbers = [1, 2, 2, 3, 3, 3, 4, 5, 5, 6, 6, 6, 6];

  // Method 1: Using Set
  const unique1 = [...new Set(numbers)];

  // Method 2: Using filter with indexOf
  const unique2 = numbers.filter((num, index) => numbers.indexOf(num) === index);

  console.log("Problem 8 - Unique Numbers:", unique1);
  return unique1;
}

// ============================================
// PROBLEM 9: Advanced Sorting
// ============================================

function sortByAverageGrade() {
  const students = [
    { name: "John", grades: [85, 90, 88] },
    { name: "Sarah", grades: [95, 92, 98] },
    { name: "Mike", grades: [75, 80, 78] },
    { name: "Emily", grades: [88, 87, 91] }
  ];

  // Calculate average for each student and sort descending
  const sorted = students
    .map(student => ({
      ...student,
      average: student.grades.reduce((sum, grade) => sum + grade, 0) / student.grades.length
    }))
    .sort((a, b) => b.average - a.average);

  console.log("Problem 9 - Students Sorted by Average Grade:");
  console.table(sorted);
  return sorted;
}

// ============================================
// PROBLEM 10: Functional Programming - Reduce
// ============================================

function calculateTotalValue() {
  const items = [
    { name: "Laptop", quantity: 2, price: 1000 },
    { name: "Mouse", quantity: 5, price: 25 },
    { name: "Keyboard", quantity: 3, price: 75 },
    { name: "Monitor", quantity: 2, price: 300 }
  ];

  // Use reduce to calculate total value
  const total = items.reduce((acc, item) => {
    return acc + (item.quantity * item.price);
  }, 0);

  console.log("Problem 10 - Total Value of Items:", total);
  return total;
}

// ============================================
// RUN ALL PROBLEMS
// ============================================

console.log("===== DATABASE INTERVIEW PROBLEMS =====\n");

filterAndMapNames();
console.log();

extractBookTitles();
console.log();

functionComposition();
console.log();

sortCarsByYear();
console.log();

findAndModifyPerson();
console.log();

sumEvenNumbers();
console.log();

isLeapYear(2024);
isLeapYear(2023);
isLeapYear(2000);
console.log();

filterUniqueNumbers();
console.log();

sortByAverageGrade();
console.log();

calculateTotalValue();
console.log("\n===== ALL PROBLEMS COMPLETED =====");
