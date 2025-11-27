# Design Specification & Mockup Reference

This document serves as the design specification and visual reference for the AI Chat Interface prototype. The design was implemented directly in code using Tailwind CSS, following a component-first approach.

## Design Philosophy

The interface follows a **modern, minimalist design** inspired by leading AI platforms (OpenAI, Anthropic, Hugging Face) with a focus on:
- **Clarity**: Clean, uncluttered interface
- **Accessibility**: High contrast, keyboard navigation
- **Responsiveness**: Mobile-first design approach
- **Consistency**: Unified design system across all components

## Visual Mockup Description

### Main Layout Structure

```
┌─────────────────────────────────────────────────────────┐
│  Header (Fixed Top)                                      │
│  [Logo] [Title] [Theme Toggle] [User Menu]              │
├──────────────┬──────────────────────────────────────────┤
│              │                                           │
│  Sidebar     │  Main Chat Area                          │
│  (320px)     │  (Flexible Width)                        │
│              │                                           │
│  ┌────────┐  │  ┌──────────────────────────────────┐   │
│  │ Model  │  │  │  Chat Messages                    │   │
│  │ Select │  │  │  ┌──────────────┐                │   │
│  └────────┘  │  │  │ User Message │                │   │
│              │  │  └──────────────┘                │   │
│              │  │  ┌──────────────┐                │   │
│              │  │  │ AI Response  │                │   │
│              │  │  └──────────────┘                │   │
│              │  └──────────────────────────────────┘   │
│              │  ┌──────────────────────────────────┐   │
│              │  │ Message Input Area                │   │
│              │  │ [Text Input] [Send Button]        │   │
│              │  └──────────────────────────────────┘   │
└──────────────┴──────────────────────────────────────────┘
```

### Component Breakdown

#### 1. Header Component
- **Height**: 64px
- **Background**: `bg-background` with border-bottom
- **Layout**: Flexbox with space-between
- **Elements**:
  - Logo/Icon (left)
  - App Title (center/left)
  - Theme Toggle (right)
  - User Menu (right)

#### 2. Sidebar Component
- **Width**: 320px (desktop), Full width overlay (mobile)
- **Background**: `bg-[hsl(var(--sidebar-bg))]`
- **Border**: Right border `border-[hsl(var(--sidebar-border))]`
- **Sections**:
  - Model Selector (top)
  - Parameters Panel (collapsible)
  - Templates Manager (collapsible)
- **Mobile**: Overlay with backdrop blur

#### 3. Chat Container
- **Max Width**: 800px (centered)
- **Padding**: 24px vertical, 16px horizontal
- **Background**: Transparent (inherits from page)
- **Scroll**: Auto-scroll to bottom on new messages

#### 4. Chat Bubbles

**User Message:**
- **Alignment**: Right
- **Background**: `bg-[hsl(var(--user-message))]` (Primary blue)
- **Text Color**: White
- **Border Radius**: `rounded-2xl` (16px)
- **Padding**: `px-4 py-3`
- **Max Width**: 80% of container
- **Elements**: Avatar icon, timestamp, copy button (on hover)

**AI Message:**
- **Alignment**: Left
- **Background**: `bg-[hsl(var(--ai-message))]` (Light gray)
- **Text Color**: Dark gray
- **Border**: `border border-border`
- **Border Radius**: `rounded-2xl` (16px)
- **Padding**: `px-4 py-3`
- **Max Width**: 80% of container
- **Elements**: Avatar icon, timestamp, copy button (on hover)

#### 5. Message Input
- **Height**: Auto (min 44px for touch targets)
- **Background**: `bg-background`
- **Border**: `border border-input`
- **Border Radius**: `rounded-lg` (8px)
- **Padding**: `px-4 py-3`
- **Layout**: Textarea + Send button (right side)
- **Focus State**: Ring with primary color

#### 6. Model Selector Dropdown
- **Background**: Dark (`bg-gray-900`)
- **Text**: White (`text-white`)
- **Border**: `border border-border`
- **Border Radius**: `rounded-lg`
- **Shadow**: `shadow-lg`
- **Hover State**: `bg-gray-800`
- **Selected State**: `bg-gray-800 font-medium`

#### 7. Parameter Sliders
- **Layout**: Vertical stack
- **Label**: Small, semibold
- **Description**: Muted text, smaller
- **Slider**: Custom styled range input
- **Value Display**: Real-time number display

#### 8. Buttons
- **Variants**: Primary, Secondary, Ghost, Danger, Outline
- **Sizes**: Small (sm), Medium (md), Large (lg), Icon
- **Border Radius**: `rounded-lg` (8px)
- **States**: Hover, Active, Disabled, Loading
- **Focus**: Ring with primary color

#### 9. Modal
- **Backdrop**: `bg-background/80 backdrop-blur-sm`
- **Modal**: `bg-card` with `border border-border`
- **Border Radius**: `rounded-xl` (12px)
- **Shadow**: `shadow-2xl`
- **Animation**: Framer Motion slide-up
- **Max Width**: 500px

## Color System

### Light Mode
```css
--background: 0 0% 100%        /* #FFFFFF - Pure white */
--foreground: 240 10% 3.9%     /* #0A0A0F - Dark gray */
--primary: 221 83% 53%          /* #3B82F6 - Blue */
--secondary: 240 4.8% 95.9%     /* #F5F5F5 - Light gray */
--muted: 240 4.8% 95.9%         /* #F5F5F5 - Light gray */
--border: 240 5.9% 90%          /* #E5E5E5 - Border gray */
```

### Dark Mode
```css
--background: 240 10% 3.9%      /* #0A0A0F - Dark */
--foreground: 0 0% 98%          /* #FAFAFA - Off-white */
--primary: 221 83% 53%          /* #3B82F6 - Blue (same) */
--secondary: 240 3.7% 15.9%     /* #1F1F23 - Dark gray */
--muted: 240 3.7% 15.9%         /* #1F1F23 - Dark gray */
--border: 240 3.7% 15.9%        /* #1F1F23 - Border */
```

## Typography

- **Font Family**: Inter (Google Fonts)
- **Base Size**: 16px
- **Line Height**: 1.5
- **Headings**: 
  - H1: 2.5rem (40px), font-weight: 700
  - H2: 2rem (32px), font-weight: 600
  - H3: 1.5rem (24px), font-weight: 600
- **Body**: 1rem (16px), font-weight: 400
- **Small**: 0.875rem (14px), font-weight: 400

## Spacing System

Based on Tailwind's spacing scale (4px base unit):
- **xs**: 4px (0.25rem)
- **sm**: 8px (0.5rem)
- **md**: 16px (1rem)
- **lg**: 24px (1.5rem)
- **xl**: 32px (2rem)
- **2xl**: 48px (3rem)

## Border Radius

- **Small**: 8px (`rounded-lg`) - Buttons, inputs
- **Medium**: 12px (`rounded-xl`) - Cards, modals
- **Large**: 16px (`rounded-2xl`) - Chat bubbles
- **Full**: 9999px (`rounded-full`) - Avatars, pills

## Shadows

- **sm**: `0 1px 2px 0 rgb(0 0 0 / 0.05)`
- **md**: `0 4px 6px -1px rgb(0 0 0 / 0.1)`
- **lg**: `0 10px 15px -3px rgb(0 0 0 / 0.1)`
- **xl**: `0 20px 25px -5px rgb(0 0 0 / 0.1)`
- **2xl**: `0 25px 50px -12px rgb(0 0 0 / 0.25)`

## Responsive Breakpoints

- **Mobile**: < 768px
  - Sidebar: Full-screen overlay
  - Single column layout
  - Reduced padding
  
- **Tablet**: 768px - 1024px
  - Sidebar: Visible, collapsible
  - Two-column layout
  
- **Desktop**: > 1024px
  - Sidebar: Fixed, always visible
  - Full layout with optimal spacing

## Animations

- **Transitions**: 150ms ease-in-out (default)
- **Hover**: Scale (0.95) on buttons
- **Focus**: Ring animation (2px primary color)
- **Modal**: Slide-up with fade (300ms)
- **Typing Indicator**: Pulse animation (1.4s infinite)

## Accessibility Features

- **Focus States**: Visible rings on all interactive elements
- **ARIA Labels**: Proper labeling for screen readers
- **Keyboard Navigation**: Tab order, Enter/Space for buttons
- **Color Contrast**: WCAG AA compliant (4.5:1 minimum)
- **Touch Targets**: Minimum 44x44px for mobile

---

**Note**: This design was implemented directly in code using Tailwind CSS. The visual mockup can be seen by running the application. For a visual representation, screenshots of the live application serve as the design reference.

