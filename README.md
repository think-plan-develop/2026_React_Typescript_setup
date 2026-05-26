tsconfig.app.json::::::::::::::::::::::::::::::::::::::::::::::::::
## 📊 TypeScript Configuration Summary

### 🎯 Output & Target
| Setting | Purpose | Value |
|---------|---------|-------|
| **target** | JS version | ES2023 (latest) |
| **lib** | Available APIs | ES2023 + DOM |
| **module** | Module format | ESNext |
| **jsx** | JSX handling | Modern (no React import) |

### ⚙️ Build & Resolution
| Setting | Purpose | Value |
|---------|---------|-------|
| **tsBuildInfoFile** | Cache location | `.tsbuildinfo` |
| **skipLibCheck** | Performance | ✅ Enabled |
| **moduleResolution** | Import resolution | Bundler-optimized |
| **noEmit** | Output files | ❌ No (Vite handles) |

### 📦 Module & Import Settings
| Setting | Purpose | Value |
|---------|---------|-------|
| **allowImportingTsExtensions** | Import `.ts` files | ✅ Allowed |
| **verbatimModuleSyntax** | Import strictness | ✅ Enforced |
| **moduleDetection** | File isolation | Force modules |
| **types** | Type definitions | Vite client |

### 🔍 Code Quality & Linting
| Setting | Purpose | Value |
|---------|---------|-------|
| **noUnusedLocals** | Unused variables | ❌ Disallowed |
| **noUnusedParameters** | Unused params | ❌ Disallowed |
| **erasableSyntaxOnly** | Type-only syntax | ✅ Required |
| **noFallthroughCasesInSwitch** | Switch safety | ✅ Enforced |

### 📁 Scope
| Setting | Value |
|---------|-------|
| **include** | `src/` folder |















tsconfig.node.json:::::::::::::::::::::::::::::::::::::::::

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

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```
