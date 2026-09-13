# Current UI Prompt - Circle Admin Panel

Build a dark, dense, operator-focused Next.js admin dashboard for Circle Admin Panel. The UI uses a collapsible left sidebar, protected dashboard shell, glass-card surfaces, muted dark backgrounds, primary cyan/purple accents, compact tables, small uppercase metadata badges, Tabler/lucide icons, shadcn-style controls, and practical admin workflows. Keep the look operational, not marketing-like.

## Global Shell

- Protected dashboard layout wraps all dashboard routes.
- Left collapsible sidebar with Circles logo, grouped navigation, active route highlighting, icon+label menu items, and profile footer.
- Sidebar groups: Dashboard, User Management, Admin Users.
- Main content has padding and full-width responsive layout.
- Shared dashboard header pattern uses page title, sidebar trigger on mobile, and SpringBoard action area.

## Auth / Login Page

- Split-screen login page.
- Left side: centered login form, Circles logo, greeting copy based on time of day, email and password fields with icons, show/hide password, Remember Me checkbox, Forgot Password link, and full-width Log In button with spinner state.
- Forgot password mode: email input, Send Verification Code button, Back to Log In link.
- Reset password mode: disabled email field, verification code, new password with show/hide toggle, Reset Password button.
- Right side on desktop: black gradient hero panel with quote-line images, animated text `Welcome to Circles Admin Panel`, supporting login copy, dotted corner decorations, footer text `Modern Admin Solutions / Powering Efficiency and Innovation`.
- Verifying auth state shows centered Loading component with `Verifying Authentication`.

## Dashboard / Overview Page

- Page header title: Dashboard.
- Three metric cards in responsive grid: Total Users, Active Venues, `$Revenue`.
- Cards use icons, compact uppercase labels, bold metric values, short descriptions, subtle borders, hover border accent.
- Below metrics: Users Overview chart card with AreaChart, primary gradient fill, month x-axis, numeric y-axis, custom tooltip, dark grid lines.

## Admin Users Page

- Header: `Admin Users` with total users badge and description.
- Actions: search input by name/email, refresh icon button, Add Admin button.
- Main glass-card table columns: S.No, Admin User, Contact Info, Role, Gender, Status, Actions.
- Rows show gradient avatar initial, name, email, optional phone, role badge, gender icon, status badge, hover-revealed edit action.
- Loading state: table skeleton rows.
- Error state: centered alert icon, failure message, error text, Try Again button.
- Empty state: user icon and search-aware copy.
- Edit admin modal: centered dark card, title `Edit Admin User`, first/last name fields, status select, Cancel and Update Details buttons.
- Add admin modal: first/last name, email, password, Cancel and Create Admin buttons.
- Delete confirmation modal exists but delete action is currently commented out in row actions.

## Users Page

- Header: `Users` with total badge and descriptive helper text.
- Actions: search input by name/email and refresh icon button.
- Main glass-card table columns: S.No, Name, Email, Phone No, Status, Reliability Score, Actions.
- Rows show gradient avatar initial, display name, email with icon, phone or dash, status badge, reliability score badge with award icon, edit status action.
- Loading, error, and empty table states are implemented.
- Edit status modal: readonly user summary, Active/Inactive segmented status buttons, Cancel and Save Changes buttons with saving spinner.

## Verification Queue Page

- Header: `Verification Queue` with pending count badge and description.
- Actions: search input by name/email and refresh icon button.
- Main glass-card table columns: S.No, Applicant, Email, Phone, Status, Actions.
- Rows show avatar initial, applicant name, email, phone or dash, status badge, approve and reject circular action buttons.
- Approve/reject buttons show per-row spinner while processing and disable all actions during processing.
- Loading, error, and empty states are implemented with retry and search-aware copy.

## Reviews Page

- Simple placeholder page.
- Content: padded container with h1 `Reviews`.

## Reports Page

- Simple placeholder page.
- Content: padded container with h1 `Reports`.

## Cities Page

- Header: `Cities` with total cities badge and description.
- Actions: search by city name/code, refresh icon button, Add City button.
- Main glass-card table columns: S.No, City Name, City Code, Status, Actions.
- Rows show city name, country/city code, Active/Inactive badge, hover-revealed edit and delete actions.
- Loading skeleton, error state with Try Again, and empty/search-empty state.
- Add/Edit City modal: title changes by mode, city name input, city/country code input, Active Status switch, Cancel and Save/Update button.
- Delete confirmation modal: confirms deleting selected city.

## Interests Page

- Header: `Interests` with group count badge and description.
- Actions: search interests, refresh icon button, New Group / Cancel toggle button.
- Optional creation panel: Create New Interest Group card with group name input, sub-interest input placeholder, theme color swatches, Create Group button.
- Main content is accordion card list of interest groups.
- Each group row has chevron, colored tag icon block, group name, sub-interest count badge, edit and delete icon buttons.
- Expanded group shows sub-interest badges with edit/delete mini actions and an Add sub-interest input/button row.
- Loading skeleton, error state with Try Again, empty/search-empty state.
- Delete confirmation modal for group/sub-interest.
- Edit modal for group/sub-interest name.

## Venues List Page

- Header: `Venues` with total spaces badge and description.
- Primary action: Add New Venue button.
- Main glass-card table columns: ID, Venue Information, Location, Actions.
- Rows use seeded local data, show venue id, name, manager, location, hover-revealed Edit, Delete, and chevron actions.
- Row click opens venue details.
- Delete uses browser confirm and removes local state item.

## Create Venue Page

- Padded page wrapping VenueForm in create mode.
- Form header: back button, title `Create New Venue`, subtitle, Save Venue button.
- Two-column responsive layout.
- Left column: venue image upload/drop area, preview card if image exists, interests/attributes tag manager, venue settings switches.
- Right column: venue name, description, address, city, region/state, postal code, latitude, longitude.
- Uses large rounded glass-card sections, visible labels, icon section headers, and primary save action.

## Venue Details / Edit Page

- Dynamic route resolves local seeded venue by id.
- Not found state: centered title `Venue not found` and supporting text.
- Details mode uses VenueForm in view mode.
- Header: back button, title `Venue Details`, subtitle, Edit Venue button.
- View mode makes fields readonly/disabled and shows existing venue info.
- If query has `?edit=true`, form switches to edit mode with Cancel and Update Venue buttons.
- Shows image/empty image, interests, settings switches, basic info, location details, and record timeline when created/updated dates exist.

## Profile Page

- Large profile screen with Back to Overview link and title `User Profile`.
- Top-right circular reliability score indicator.
- Left column: large circular avatar with upload/remove popover, verified check badge, and Bio card.
- Right column: Personal Information card with full name, DOB, phone, email blocks using icons, and Edit Profile button.
- Lower section: INTERESTS heading with colored rounded interest tiles.
- Currently uses a mix of auth user data and dummy fallback profile/interests.

## Current Visual Language

- Dark mode first, glass-card containers, soft borders, subtle primary glow, compact text, high-density admin tables.
- Common page pattern: title + count badge + description, right-side search/refresh/add actions, table/list in glass-card, skeleton/error/empty states, centered dark modals.
- Avoid replacing this with generic AI dashboard UI. Preserve compact admin density, direct labels, domain terms, and practical workflow states.
