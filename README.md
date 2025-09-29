# React Component Development Assignment

A modern React component library featuring InputField and DataTable components built with TypeScript, TailwindCSS, and Storybook.

## 🚀 Features

### InputField Component
- **Multiple variants**: filled, outlined, ghost
- **Flexible sizes**: small, medium, large  
- **States**: disabled, invalid, loading
- **Enhanced UX**: clear button, password toggle
- **Full accessibility**: ARIA labels, keyboard navigation
- **TypeScript**: Comprehensive type definitions

### DataTable Component
- **Column sorting**: ascending, descending, no sort
- **Row selection**: single and multiple selection modes
- **Loading states**: elegant loading and empty state handling
- **Custom rendering**: flexible cell content customization
- **Responsive design**: works across all device sizes
- **TypeScript**: Generic type support for data safety

## 🛠️ Tech Stack

- **React 18** with TypeScript
- **TailwindCSS** for styling
- **Storybook** for component documentation
- **Vitest** & React Testing Library for testing
- **Lucide React** for icons
- **clsx** for conditional classnames

## 📦 Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Start Storybook
npm run storybook

# Run tests
npm run test
```

## 🏗️ Project Structure

```
src/
├── components/
│   ├── InputField/
│   │   ├── InputField.tsx
│   │   ├── InputField.stories.tsx
│   │   ├── InputField.test.tsx
│   │   └── index.ts
│   ├── DataTable/
│   │   ├── DataTable.tsx
│   │   ├── DataTable.stories.tsx  
│   │   ├── DataTable.test.tsx
│   │   └── index.ts
│   └── index.ts
├── test/
│   └── setup.ts
└── App.tsx (Demo application)
```

## 🧪 Component APIs

### InputField Props

```typescript
interface InputFieldProps {
  value?: string;
  onChange?: (e: React.ChangeEvent<HTMLInputElement>) => void;
  label?: string;
  placeholder?: string;
  helperText?: string;
  errorMessage?: string;
  disabled?: boolean;
  invalid?: boolean;
  loading?: boolean;
  variant?: 'filled' | 'outlined' | 'ghost';
  size?: 'sm' | 'md' | 'lg';
  type?: string;
  showClearButton?: boolean;
  showPasswordToggle?: boolean;
}
```

### DataTable Props

```typescript
interface DataTableProps<T> {
  data: T[];
  columns: Column<T>[];
  loading?: boolean;
  selectable?: boolean;
  onRowSelect?: (selectedRows: T[]) => void;
  emptyMessage?: string;
}

interface Column<T> {
  key: string;
  title: string;
  dataIndex: keyof T;
  sortable?: boolean;
  render?: (value: any, record: T, index: number) => React.ReactNode;
  width?: string | number;
  align?: 'left' | 'center' | 'right';
}
```

## 🎨 Design System

### Color System
- **Primary**: Blue (#3B82F6) for actions and focus states
- **Secondary**: Gray (#6B7280) for text and borders  
- **Success**: Green (#10B981) for positive states
- **Error**: Red (#EF4444) for validation errors
- **Neutral**: Comprehensive gray scale for backgrounds

### Typography
- Consistent font sizes across components
- Proper line heights (150% body, 120% headings)
- Maximum 3 font weights for clarity

### Spacing
- 8px grid system for consistent spacing
- Responsive breakpoints for mobile-first design
- Intentional white space for improved readability

## ✅ Accessibility Features

- **Keyboard Navigation**: Full keyboard support for all interactive elements
- **Screen Readers**: Comprehensive ARIA labels and descriptions
- **Focus Management**: Visible focus indicators and logical tab order
- **Color Contrast**: WCAG compliant color combinations
- **Error States**: Clear error messaging and validation feedback

## 🧪 Testing

The components include comprehensive test suites covering:

- **Unit Tests**: Component rendering and prop handling
- **Integration Tests**: User interactions and state changes
- **Accessibility Tests**: ARIA attributes and keyboard navigation
- **Edge Cases**: Loading states, empty data, and error conditions

```bash
# Run tests
npm run test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode  
npm run test:watch
```

## 📚 Storybook Documentation

Interactive component documentation with live examples:

```bash
# Start Storybook locally
npm run storybook

# Build Storybook for deployment
npm run build-storybook
```

### Available Stories

**InputField**:
- Default state
- All variants (filled, outlined, ghost)
- All sizes (sm, md, lg)
- State variations (loading, error, disabled)
- Interactive features (clear button, password toggle)

**DataTable**:
- Basic table with data
- Selectable rows
- Loading and empty states
- Custom cell rendering
- Large dataset performance
- Sorting demonstration

## 🚀 Usage Examples

### Basic InputField

```tsx
import { InputField } from './components';

function LoginForm() {
  const [email, setEmail] = useState('');
  
  return (
    <InputField
      label="Email Address"
      type="email"
      value={email}
      onChange={(e) => setEmail(e.target.value)}
      placeholder="Enter your email"
      variant="outlined"
      showClearButton={true}
    />
  );
}
```

### Basic DataTable

```tsx
import { DataTable, Column } from './components';

interface User {
  id: number;
  name: string;
  email: string;
}

const columns: Column<User>[] = [
  { key: 'name', title: 'Name', dataIndex: 'name', sortable: true },
  { key: 'email', title: 'Email', dataIndex: 'email', sortable: true },
];

function UserTable() {
  const [users, setUsers] = useState<User[]>([]);
  
  return (
    <DataTable
      data={users}
      columns={columns}
      selectable={true}
      onRowSelect={(selected) => console.log(selected)}
    />
  );
}
```

## 🎯 Development Approach

### Component Design Philosophy
- **Composable**: Components work together seamlessly
- **Flexible**: Extensive customization through props
- **Accessible**: Built-in accessibility best practices
- **Performant**: Optimized rendering and minimal re-renders
- **Type-Safe**: Comprehensive TypeScript definitions

### Code Quality
- **ESLint**: Consistent code formatting and best practices
- **TypeScript**: Strict type checking for runtime safety
- **Testing**: Comprehensive test coverage for reliability
- **Documentation**: Clear inline documentation and examples

### Modern Patterns
- **React Hooks**: Efficient state management
- **Generic Types**: Type-safe component APIs
- **Compound Components**: Flexible composition patterns
- **Forward Refs**: Proper ref handling for integration

## 📈 Performance Considerations

- **Bundle Size**: Minimal dependencies and tree-shaking support
- **Rendering**: Optimized re-renders with proper memoization
- **Accessibility**: Efficient DOM structure for screen readers
- **Mobile Performance**: Touch-friendly interactions and responsive design

## 🤝 Contributing

This project follows modern React development practices:

1. **Component Structure**: Each component in its own directory
2. **Testing**: Comprehensive test coverage required
3. **Documentation**: Storybook stories for all components
4. **TypeScript**: Strict typing for all interfaces
5. **Accessibility**: WCAG compliance for all interactions

The components are production-ready and demonstrate professional-level React development with attention to user experience, performance, and maintainability.