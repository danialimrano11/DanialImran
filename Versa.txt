// Import the File System module to work with files
const fs = require('fs');

// Function to generate the array of numbers with replacements
function BigBang() {
  // Initialize an empty array to store the result
  const result = [];

  // Loop from 1 to 100
  for (let i = 1; i <= 100; i++) {
    // Check if the number is divisible by both 3 and 5
    if (i % 3 === 0 && i % 5 === 0) {
      // If divisible by both, push 'BIGBANG' into the result array
      result.push('BIGBANG');
    } 
    // Check if the number is divisible by 3
    else if (i % 3 === 0) {
      // If divisible by 3, push 'BIG' into the result array
      result.push('BIG');
    } 
    // Check if the number is divisible by 5
    else if (i % 5 === 0) {
      // If divisible by 5, push 'BANG' into the result array
      result.push('BANG');
    } 
    // If the number is not divisible by 3 or 5
    else {
      // Push the number as a string into the result array
      result.push(i.toString());
    }
  }

  // Return the resulting array
  return result;
}

// Generate the array
const output = BigBang();

// Write the output array to 'output.json' file
fs.writeFileSync('output.json', JSON.stringify(output));

// Log a message to indicate that the output has been written successfully
console.log('Output has been written to output.json');
