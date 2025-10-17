# Package Example

```
math-lib/
├── package.json
├── index.js          ✅ (entry point of the package)
└── src/
    ├── add.js
    └── subtract.js

# Create a simple JavaScript package with multiple modules

# 1. Create the package folder and move into it
mkdir math-lib && cd math-lib

# 2. Initialize it as an npm package
npm init -y

# Edit package.json so it contains:
# {
#   "name": "math-lib",
#   "version": "1.0.0",
#   "type": "module",
#   "main": "index.js"
# }

# 3. Create the src folder for internal modules
mkdir src

# 4. Create the module files
touch src/add.js src/subtract.js

# 5. Add the following to src/add.js
echo "export function add(a, b) {
  return a + b;
}" > src/add.js

# 6. Add the following to src/subtract.js
echo "export function subtract(a, b) {
  return a - b;
}" > src/subtract.js

# 7. Create the main entry point file
touch index.js

# 8. Add the following to index.js
echo "// index.js — entry point for the math-lib package
export { add } from './src/add.js';
export { subtract } from './src/subtract.js';" > index.js

# 9. Create a demo file to test the package
touch demo.js

# 10. Add the following to demo.js
echo "// demo.js — simple test script
import { add, subtract } from './index.js';

console.log('Add:', add(10, 5));
console.log('Subtract:', subtract(10, 5));" > demo.js

# 11. Run the demo
node demo.js

# Expected output:
# Add: 15
# Subtract: 5

```