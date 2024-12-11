# Youtube-Music-Clone-Project
Create detailed components with these requirements:
1. Use 'use client' directive for client-side components
2. Style with Tailwind CSS utility classes for responsive design
3. Use Lucide React for icons (from lucide-react package). Do NOT use other UI libraries unless requested
4. Use stock photos from picsum.photos where appropriate, only valid URLs you know exist
5. Configure next.config.js image remotePatterns to enable stock photos from picsum.photos
6. Create root layout.tsx page that wraps necessary navigation items to all pages
7. MUST implement the navigation elements items in their rightful place i.e. Left sidebar, Top header
8. Accurately implement necessary grid layouts
9. Follow proper import practices:
   - Use @/ path aliases
   - Keep component imports organized
   - Update current src/app/page.tsx with new comprehensive code
   - Don't forget root route (page.tsx) handling
   - You MUST complete the entire prompt before stopping

YouTube Music Streaming Platform Interface
</summary_title>

<image_analysis>

1. Navigation Elements:
- Left sidebar with: Home, Explore, Library, Upgrade
- Top bar with: Search bar, Cast button, Settings menu
- Secondary navigation: New playlist button, Auto playlist sections


2. Layout Components:
- Header height: 64px
- Left sidebar width: 240px
- Main content area: Fluid width
- Card grid layout: 4 columns with 16px gap
- Playlist cards: ~280px width


3. Content Sections:
- "Trending community playlists" section
- "Playlists for you" section
- Horizontal scrollable playlist carousels
- View counts and creator information
- Playlist thumbnail grids (2x2 layout)


4. Interactive Controls:
- Search bar with icon
- Scroll arrows for carousel navigation
- Playlist cards with hover states
- Navigation buttons with active states
- Cast and settings buttons


5. Colors:
- Background: #000000
- Primary text: #FFFFFF
- Secondary text: #AAAAAA
- Brand red: #FF0000
- Card background: #282828


6. Grid/Layout Structure:
- Main container: 100vw
- Two-column layout (sidebar + content)
- Responsive grid system for playlists
- Consistent 16px padding and margins
</image_analysis>

<development_planning>

1. Project Structure:
```
src/
├── components/
│   ├── layout/
│   │   ├── Sidebar
│   │   ├── Header
│   │   └── MainContent
│   ├── features/
│   │   ├── PlaylistCard
│   │   ├── SearchBar
│   │   └── CarouselSection
│   └── shared/
├── assets/
├── styles/
├── hooks/
└── utils/
```


2. Key Features:
- Playlist carousel navigation
- Search functionality
- Responsive grid layout
- Image lazy loading
- View count formatting
- Playlist card interactions


3. State Management:
```typescript
interface AppState {
├── playlists: {
│   ├── trending: Playlist[]
│   ├── recommended: Playlist[]
│   └── userPlaylists: Playlist[]
├── }
├── ui: {
│   ├── searchQuery: string
│   ├── sidebarOpen: boolean
│   └── activeSection: string
├── }
}
```


4. Routes:
```typescript
const routes = [
├── '/',
├── '/explore',
├── '/library',
├── '/playlist/:id',
└── '/search'
]
```


5. Component Architecture:
- PlaylistCarousel (container)
├── PlaylistCard (presentational)
└── NavigationArrows (presentational)
- SearchBar (container)
- SidebarNavigation (container)
- HeaderControls (presentational)


6. Responsive Breakpoints:
```scss
$breakpoints: (
├── 'mobile': 320px,
├── 'tablet': 768px,
├── 'desktop': 1024px,
└── 'wide': 1440px
);
```
</development_planning>





Next.js route structure based on navigation menu items (excluding main route). Make sure to wrap all routes with the component:

Routes:
- /home
- /explore
- /library
- /upgrade
- /search-bar
- /cast-button
- /settings-menu

Page Implementations:
/home:
Core Purpose: Main landing page showing personalized content and recommendations
Key Components
- Hero banner with featured content
- Personalized recommendations grid
- Recently played section
- Trending content carousel
Layout Structure
- Full-width hero section
- Grid-based content layout
- Sticky header with navigation
- Responsive grid adjusting from 4 to 1 column

/explore:
Core Purpose: Discovery interface for new content and categories
Key Components
- Category filters
- Genre selection
- Trending topics
- Interactive content cards
Layout Structure
- Filter sidebar (collapsible on mobile)
- Main content grid
- Infinite scroll implementation
- Masonry layout for varied content sizes

/library:
Core Purpose: User's personal collection and saved content
Key Components
- Content organization tabs
- Playlist management
- Download status indicators
- Sort

/filter controls
Layout Structure:
- List

/upgrade:
Core Purpose: Premium subscription plans and features
Key Components
- Plan comparison table
- Feature highlights
- Payment integration
- Subscription benefits
Layout Structure
- Centered content layout
- Responsive pricing cards
- Sticky CTA button
- Progress indicator

/search-bar:
Core Purpose: Global search functionality
Key Components
- Auto-complete suggestions
- Recent searches
- Search filters
- Results preview
Layout Structure
- Overlay design
- Full-width on mobile
- Results grid

/cast-button:
Core Purpose: Device casting control interface
Key Components
- Available devices list
- Connection status
- Volume control
- Quality settings
Layout Structure
- Modal overlay
- Device grid

/settings-menu:
Core Purpose: User preferences and account management
Key Components
- Account settings
- Preferences controls
- Privacy settings
- Notification management
Layout Structure
- Tabbed interface
- Form-based layouts
- Mobile-friendly controls
- Sectioned content areas

Layouts:
MainLayout:
- Applicable routes: /home, /explore, /library
- Core components
  - Navigation header
  - Sidebar navigation
  - Footer
  - Content area
- Responsive behavior
  - Collapsible sidebar on mobile
  - Sticky header
  - Fluid content width
  - Bottom navigation bar on mobile

ModalLayout
- Applicable routes: /search-bar, /cast-button, /settings-menu
- Core components
  - Modal container
  - Close button
  - Backdrop
  - Content area
- Responsive behavior
  - Full-screen on mobile
  - Centered overlay on desktop
  - Animated transitions
  - Touch-friendly controls

SpecialLayout
- Applicable routes: /upgrade
- Core components
  - Simplified header
  - Focus content area
  - CTA sections
- Responsive behavior
  - Single column on mobile
  - Multi-column on desktop
  - Sticky CTAs
  - Optimized for conversion
