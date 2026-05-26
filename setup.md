# 🔧 TypeScript Configuration Guide

---

## 🎯 **Output & Compilation**
| Setting | Purpose |
|---------|---------|
| **target** | Sets the JavaScript version TypeScript compiles to |
| **lib** | Adds typings for built-in JavaScript APIs |
| **module** | Defines the module system like ES Modules |
| **noEmit** | Prevents TypeScript from generating JS output |

---

## 📦 **Module System & Resolution**
| Setting | Purpose |
|---------|---------|
| **moduleResolution** | Controls how imported modules are resolved |
| **allowImportingTsExtensions** | Allows importing files with .ts extensions |
| **verbatimModuleSyntax** | Keeps import/export syntax unchanged |
| **moduleDetection** | Forces files to behave as ES modules |

---

## ⚡ **Performance & Optimization**
| Setting | Purpose |
|---------|---------|
| **tsBuildInfoFile** | Stores incremental build cache for faster recompilation |
| **skipLibCheck** | Skips type checking of library declaration files |

---

## 📋 **Type Checking & Quality**
| Setting | Purpose |
|---------|---------|
| **types** | Includes global typings such as Node.js types |
| **noUnusedLocals** | Reports unused local variables |
| **noUnusedParameters** | Reports unused function parameters |
| **erasableSyntaxOnly** | Allows only syntax removable during transpilation |
| **noFallthroughCasesInSwitch** | Prevents accidental switch-case fallthrough |

---

## 📁 **Project Scope**
| Setting | Purpose |
|---------|---------|
| **include** | Specifies which files TypeScript should process |