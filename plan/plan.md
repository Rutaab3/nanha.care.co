<center><img src="logo.png" alt="logo" width="300px"></center>

**`NanhaCare`— a Pakistan-focused childcare platform. The app connects parents with verified babysitters, hosts a baby product marketplace, and provides doctor-written parenting blog. The platform is in English with Urdu support planned.**


## 🎨 BRAND & DESIGN SYSTEM

- **Brand Name:** `NanhaCare`
- **Logo:** `Text-based logo with a mother and a baby`
- **Color Palette:**
```css
:root {
    --sky-blue: #7EB8DA;
    --baby-pink: #F8B1C8;
    --mint-green: #C6F3D3;
    --off-white: #FFF9F2;
    --sunshine-yellow: #FFE97F;
    --slate-grey: #AAAAAA;
    --dark-text: #555555;
}
```
- **Typography:**
```text
Poppins (headings) 
Inter (body)
```
- **Style:** 
```text
Clean, modern, family-friendly. 
Cards with soft shadows, rounded corners, warm imagery placeholders.
```


## 🌐 PUBLIC PAGES (No Login Required)


> **HOME PAGE**
- `Hero section:` "Find Trusted & Verified Babysitters in Pakistan" with two CTAs: "Find a Babysitter" and "Become a Babysitter"
- `Safety Features section:` Triple-Verified, Ratings & Reviews, Emergency Response System (3 feature cards)
- `How It Works:` 3-step visual (Search → Verify → Book)
- `Verification Process:` 4-step cards (CNIC, Police Clearance, Interview, Training & Certification)
- `Featured Babysitters:` horizontal scroll card grid showing name, city, experience, hourly rate (PKR), rating, specialization
- `Coming Soon features:` Background Checks, Activity Reports, Parent Community, Live GPS Tracking, Video Profiles, Multilingual Platform
- `Testimonials:` 3 parent quotes with name and city
- `Footer:` Quick Links, More Links, Product Categories, Terms of Service, Privacy Policy, Sitemap

> **BABYSITTERS LISTING PAGE**
 - `Filter by:` City (Karachi, Lahore, Islamabad, etc.), Experience level, Hourly rate range, Specialization, Availability (Today, This Week, Custom)
- `Sort by:` Rating, Price (low/high), Experience, Reviews count
- `Each card:` Profile photo, Verification badge (NC-CITY-ID), Name, City, Experience, Star rating + review count, Specialization tags, Hourly rate in PKR, "View Profile" button
- `Babysitter detail profile page:` Full bio, certifications, photo, working hours, all reviews, booking calendar widget

> **PRODUCTS MARKETPLACE PAGE**
 - `Category filters:` Newborns (0–12M), Toddlers (1–3Y), Preschoolers (3–5Y), School Age (5–10Y), All Products
- `Product card:` Image, name, price (PKR), shop name, rating, "Add to Cart" button
- `Product detail page:` Image gallery, description, seller info, reviews, related products
- `Cart:` Add/remove items, quantity, total, checkout flow
- `Checkout:` Shipping address (Pakistan cities), order summary, payment method placeholder (Cash on Delivery + Card)

> **BLOG PAGE**
- `Published doctor`-written articles listed in card grid
- `Each card:` Cover image, title, author (doctor name + photo), specialty, publish date, read time, category tag, short excerpt
- `Blog detail page:` Full article, author bio box, related articles, comment section (for logged-in parents)
- `Categories:` Newborn Care, Infant Nutrition, Sleep Training, Child Development (0–12 years), Vaccinations, Mental Health

> **ABOUT PAGE**
- `Mission statement`
- `values`
- `team section`
- `Pakistan-specific trust signals` **(NADRA integration mention, local police clearance)**

> **CONTACT PAGE**
- `Contact form:` name, email, phone, subject (dropdown), message
- FAQ accordion section
- Emergency numbers prominently shown

> **PRICING PAGE**
- Subscription tiers for `parents` **(Free, Basic, Premium)**
- `Shop owner` listing packages

> **TRAINING PAGE**
- Info for aspiring babysitters about: 
  - The training program steps.
  - Requirements. 
  - What to expect. 
  - Apply button

## 🔐 AUTH SYSTEM

> **Register**
- `Admin` is assigned by system.
- Single / register page for Parent | `Babysitter` | `Shop Owner` | `Doctor` | `Moderator` | `Support Agent` 
- `Moderator` | `Support Agent` (assigned by `Admin` only)
- Parent | `Babysitter` | `Shop Owner` | `Doctor` (choose from dropown)
- `Fields:` Full name, email, password, phone number, city, role
- Role-specific onboarding after registration:
  - `Babysitter`: CNIC number, experience, specialization, 
    certifications upload, hourly rate, availability
  - `Shop Owner:` Business name, shop category, CNIC/NTN, 
    bank details
  - `Doctor:`  Medical license number, specialization, 
    hospital/clinic affiliation, profile photo
  - `Parent:` Number of children, age ranges

> **Login**
- `Login page:` email + password, forgot password link
- `Email verification` for the 1st time before dashboard access
- `After login,` redirect based on role to respective dashboard

## 👤 DASHBOARD 1 — ADMIN
- `Route`: /dashboard/admin
- `Access`: Admin role only (cannot self-register, assigned by system)

> **Sidebar Sections:**
- Overview
- User Management
- Role Assignment
- Moderation Oversight
- Reports & Analytics
- Platform Settings
- Announcements

> **Overview Panel:**
- `Stats cards:` Total Users, Total Bookings, Active Listings, Pending Reviews, Revenue (this month), Open Support Tickets
- `Recent activity feed:` last 20 platform events with timestamps
- `Platform health status:` (uptime, DB status)

> **User Management:**
- `Full searchable:` filterable table of ALL users (all roles)
- `Columns:` Name, Email, Role, City, Join Date, Status, Actions
- `Admin can:` View profile, Suspend account, Ban account (permanent), Restore account, Delete account
- `Ban system:` Requires ban reason + duration selection (Temporary: 7/30/90 days | Permanent). Banned users see a "Your account has been suspended" screen on login.
- `Filters:` By role, city, status (active/suspended/banned/pending)

> **Role Assignment (EXCLUSIVE to Admin):**
- `Search` any user by name or email
- `Assign or change` their role from a dropdown: Parent | Babysitter | Shop Owner | Doctor | Moderator | Support Agent | Admin
- `All role changes` are logged with timestamp + admin name
- `Cannot demote another` Admin without superadmin flag

> **Moderation Oversight:**
- `View all Moderator actions` (approvals, rejections, flags)
- `Override any Moderator decision` (approve a rejected item, reject an approved item)
- `Assign specific moderators` to categories (e.g., Mod A handles Blogs, Mod B handles Shop listings)
- `Moderator performance table:` items reviewed, avg review time, approval rate

> **Reports & Analytics:**
- `Charts:` New users per week, bookings per day, top selling products, most read blogs, city-wise usage
- `Export reports as CSV.`
- `Revenue breakdown:` subscription fees, listing fees, transaction percentages
- `Flagged content report:` how many items flagged, resolved, still pending

> **Platform Settings:**
- `Commission` percentage per sale.
- `Babysitter booking fee` settings.
- `Subscription plan management.` (edit pricing tiers)
- `Platform maintenance mode` toggle.
- `Email notification templates editor.`
- `Terms of Service & Privacy Policy editor.` (rich text)

> **Announcements:**
- `Send platform-wide notifications` to all users or specific roles
- `Scheduled announcements` (set future publish time)

## 👤 DASHBOARD 2 — MODERATOR

- `Route:` /dashboard/moderator
- `Access:` Assigned by Admin only

> **Sidebar Sections:**
- Review Queue
- Published Content
- Flagged Items
- User Reports
- My Activity Log

> **Review Queue (Core function):**
- `Two tabs:` "Shop Listings" | "Blog Posts"
- `Each item in queue shows:` Submitted by, submission date, content preview, category
- `Action buttons:` "Approve & Publish" | "Reject with Reason" | "Request Revision" (sends message to submitter)
- `Rejection requires a mandatory reason` from a dropdown (Inappropriate Content, Incomplete Information, Low Quality, Policy Violation, Other) + optional text note
- `Approved items go LIVE` immediately on the public site
- `Rejected items notify` the submitter with reason

> **Published Content:**
- `Table of all currently live listings and blogs.`
- `Can unpublish any item` (moves back to review or archives)
- `Search and filter` by category, author, date

> **Flagged Items:**
- `Items reported by parents` (inappropriate product, misleading blog, spam)
- `Each flag shows:` Who flagged, reason, date, content preview
- `Actions:` Dismiss flag, Unpublish content, Escalate to Admin, Warn user, Ban user (ban button → sends request to Admin for final approval)

> **User Reports:**
- `Reports filed against babysitters or shop owners by parents.`
- `See full report detail`, link to user profiles
- `Take action:` Warn, Suspend (sends to Admin for approval), Mark Resolved, Dismiss

> **My Activity Log:**
- `Personal history of all actions taken with timestamps`

## 👤 DASHBOARD 3 — BABYSITTER

- `Route:` /dashboard/babysitter
- `Access:` Verified babysitter accounts

> **Sidebar Sections:**
- My Overview
- Bookings
- My Profile
- Earnings
- Reviews
- Notifications

> **My Overview:**
- `Status card:` Profile Verified ✅ / Pending Verification ⏳ / Rejected ❌ (with reason shown if rejected)
- `Stats:` Total bookings, Active bookings, Completed sessions, Average rating, Total earnings (PKR)
- `Upcoming booking countdown card`

> **Bookings Tab:**
- `Tabs:` Pending Requests | Confirmed | Completed | Cancelled
- `Each booking card shows:` Parent name, child age(s), date & time, duration, location (city/area), total fee, notes from parent
- `Actions on Pending:` Accept | Decline (with reason)
- `Actions on Confirmed:` Mark Complete | Report Issue
- `History:` Full paginated table of all past bookings

> **My Profile:**
- `Edit all profile fields:` bio, photo, specializations (multi-select tags: Newborn Care, Toddler Activities, Montessori, First Aid, etc.), certifications upload, hourly rate (PKR), languages spoken, working hours (day + time range availability calendar)
- `Profile completion progress bar` (e.g., 78% complete)
- `Public profile preview button` (see how parents see it)

> **Earnings Tab:**
- `Monthly earnings chart` (bar graph)
- `Table:` booking date, parent, duration, amount, payment status (Paid/Pending)
- `Payout request button` (minimum threshold)
- `Bank account` / `JazzCash` / `EasyPaisa details management`

> **Reviews Tab:**
- `All reviews` left by parents. (star rating + comment)
- `Reply to review` option. (public reply visible on profile)
- `Flag inappropriate review option.`

## 👤 DASHBOARD 4 — PARENT (Simple User)

- `Route:` /dashboard/parent
- `Access:` Registered parents

> **Sidebar Sections:**
- Home
- My Bookings
- My Orders
- Saved Babysitters
- Blog Reads / Bookmarks
- My Children Profiles
- Reviews I've Left
- Account Settings

> **Home:**
- `Welcome card`, `subscription plan badge`
- `Quick action buttons:` "Book a Babysitter", "Browse Products", "Read Latest Blogs"
- `Upcoming booking(s) summary card`
- `Recommended babysitters` based on city
- Featured `new blog posts`

> **My Bookings:**
- `Tabs:` Upcoming | Active | Completed | Cancelled
- `Full booking detail` per card
- `"Leave a Review"` button on completed bookings
- `"Report Issue"` button
- `Rebook a previous` babysitter shortcut

> **My Orders:**
- `Order list from marketplace:` order ID, date, items, total, status (Processing/Shipped/Delivered/Returned)
- `Order detail page` with item breakdown and tracking status
- `Return/Refund` request button

> **My Children Profiles:**
- `Add child:` name, date of birth (age auto-calculated), gender, any allergies or special needs (text field)
- `These profiles are shared with babysitter when booking`

> **Saved Babysitters:**
- `Shortlist of bookmarked` babysitter profiles
- `Quick-book from this list`

> **Blog Bookmarks:**
- `Saved blog articles list`

> **Account Settings:**
- `Edit profile:` name, phone, city, profile photo
- `Change password`
- `Notification preferences` (email/SMS/in-app)
- `Delete account request` (requires Admin approval to process)


## 👤 DASHBOARD 5 — SHOP OWNER

- `Route:` /dashboard/shop-owner
- `Access:` Registered shop owners (profile pending Moderator review 
before going live)

> **Sidebar Sections:**
- Shop Overview
- My Products
- Add New Product
- Orders Management
- Earnings & Payouts
- Shop Profile
- Reviews & Ratings

> **Shop Overview:**
- `Stats:` Total products listed, Live products, Pending review, 
  Total orders, Revenue this month, Avg product rating
- `Best-selling products chart`
- `Pending orders` alert card

> **My Products:**
- `Table:` Product image, name, category, price, stock qty, status (Draft | Under Review | Live | Rejected), actions
- `Status badge with color coding`
- `Edit`, `Duplicate`, `Archive`, `Delete` actions
- `Filter` by status, category

> **Add New Product (Submit for Review):**
- `Form:` 
  - Product name 
  - description (rich text) 
  - price (PKR) 
  - sale price (optional) 
  - stock quantity 
  - category (Newborns/Toddlers/Preschoolers/School Age) 
  - age-appropriateness tags up to 5 
  - product images upload 
  - weight (for shipping) is_featured checkbox
- `Submit button` → `status becomes` "Under Review" → `Moderator sees it in queue`
- `Draft save option`

> **Orders Management:**
- `Incoming orders table:` 
  - order ID
  - buyer (parent name)
  - product
  - qty
  - date
  - status
  - total
- `Update order status:` Processing → Shipped → Delivered
- `Cancel order` (with reason, triggers refund flow)

> **Earnings & Payouts:**
- `Revenue chart` by week/month
- `Platform commission` deducted breakdown
- `Payout` to `bank`/`JazzCash`/`EasyPaisa`
- `Transaction history table`

> **Shop Profile:**
- `Shop name`, `logo`, `banner image`, `description`, `contact info`,` return policy text`
- `Shop URL slug` (nanhacare.com/shop/your-shop-name)


## 👤 DASHBOARD 6 — DOCTOR
- `Route:` /dashboard/doctor
- `Access:` Registered and verified doctors

> **Sidebar Sections:**
- Overview
- My Blog Posts
- Write New Post
- Comments
- My Profile
- Analytics

> **Overview:**
- `Stats:` Total articles written, Published, Under Review, Total reads, Total likes, Comments to respond to
- `Most read article card`
- `Notification` if a post was rejected (with reason)

> **My Blog Posts:**
- `Table:` Title, category, submitted date, status (Draft | Under Review | Published | Rejected), views, likes, actions
- `Edit` draft, `View` live article, `Delete` draft

> **Write New Post:**
- `Rich text editor` (with formatting: H1/H2, bold, italic, 
  bullet lists, image insertion, blockquotes)
- `Fields:` 
  - Title 
  - Slug (auto-generated from title) 
  - Cover image upload, 
  - Category (dropdown: Newborn Care, Infant Nutrition, Sleep Training, Child Development, Vaccinations, Mental Health, etc.), 
  - Tags (multi-input), Estimated read time (auto-calc), Summary/Excerpt (max 200 chars)
- `Save as Draft` | Submit for Review
- `Submitted posts go to Moderator review queue`

> **Comments:**
- `All comments` on doctor's articles listed with parent name, date, and content.
- `Reply option` (public reply under comment)
- `Flag/report comment`

> **My Profile:**
- `Edit:` 
  - Profile photo 
  - bio 
  - specialization 
  - PMDC registration number 
  - hospital/clinic name and city 
  - years of experience 
  - languages spoken
- `Public profile page link`

> **Analytics:**
- `Per-article` 
  - **stats:** views over time, likes, shares
- `Top performing categories`
- `Audience city breakdown` (where readers are from)


## 👤 DASHBOARD 7 — CONTACT & SUPPORT AGENT

- `Route:` /dashboard/support
- `Access:` Assigned by Admin only

> **Sidebar Sections:**
- Inbox (All Tickets)
- Open Tickets
- Resolved Tickets
- FAQ Management
- Announcements
- Escalation Queue

> **Inbox:**
- `All contact form` submissions and in-app support requests
- `Each ticket:` 
  - Ticket ID 
  - Sender name + role 
  - Subject 
  - Date 
  - Priority (`Low`/`Medium`/`High`/`Urgent`), 
  - Status (`New`/`Open`/`In Progress`/`Resolved`/`Closed`)
- `Open ticket:` full message thread, reply box (with templates), 
  internal notes field (not visible to user), 
  assign to another agent

> **Ticket Management:**
- `Filter by:` 
  - status 
  - priority 
  - user role 
  - date range
- `Bulk actions:` Close, Reassign, Mark as spam
- `Auto-assign tickets based on category` (Booking Issues → Support Agent A, Shop Disputes → Support Agent B)
- `SLA timer` showing time since ticket opened

> **Escalation Queue:**
- `Tickets escalated` to Admin or requiring Moderator action
- `Flag ticket to Admin`, add escalation note

> **FAQ Management:**
- `Add`, `edit`, `delete` `FAQ` entries (shown on public `FAQ` page)
- `Organize FAQs by category` (Bookings, Payments, Accounts, Safety, etc.)
- `Draft` / `Published` status per `FAQ` entry


## 🔔 NOTIFICATIONS SYSTEM

- `In-app notification bell icon` in all dashboards.
- `Notification types per role:`
  - `Parent:` Booking confirmed, Order shipped, New blog published
  - `Babysitter:` New booking request, Review received, Verification status update
  - `Shop Owner:` New order, Product approved/rejected, Review left
  - `Doctor:` Blog post approved/rejected, New comment
  - `Moderator:` New item in review queue (with count badge)
  - `Support:` New support ticket assigned
  - `Admin:` User ban requests from Moderators, Critical reports, Revenue milestones
- `Mark as read`, Mark all as `read`, `Delete` notification


## 🗄️ DATABASE SCHEMA (Supabase)

> **Tables:**
- **users** (`id`, `email`, `full_name`, `phone`, `city`, `role`, `status`, `avatar_url`, `created_at`)
- **babysitter_profiles** (`user_id`, `cnic`, `experience_years`, `specializations[]`, `certifications[]`, `hourly_rate`, `availability`, `bio`, `rating`, `verified_status`, `verification_badge_id`)
- **bookings** (`id`, `parent_id`, `babysitter_id`, `children_ids[]`, `date`, `start_time`, `end_time`, `location`, `status`, `total_fee`, `notes`, `created_at`)
- **children** (`id`, `parent_id`, `name`, `dob`, `gender`, `allergies`, `special_needs`)
- **products** (`id`, `shop_owner_id`, `name`, `description`, `price`, `sale_price`, `stock`, `category`, `age_tags[]`, `images[]`, `status`, `rating`, `created_at`)
- **orders** (`id`, `parent_id`, `items[]`, `total`, `shipping_address`, `status`, `created_at`)
- **order_items** (`id`, `order_id`, `product_id`, `qty`, `price`)
- **shops** (`id`, `owner_id`, `name`, `logo`, `banner`, `description`, `slug`, `return_policy`, `verified`)
- **blog_posts** (`id`, `doctor_id`, `title`, `slug`, `content`, `cover_image`, `category`, `tags[]`, `summary`, `read_time`, `status`, `views`, `likes`, `created_at`)
- **comments** (`id`, `post_id`, `parent_id`, `content`, `created_at`, `is_flagged`)
- **reviews_babysitter** (`id`, `booking_id`, `parent_id`, `babysitter_id`, `rating`, `comment`, `created_at`)
- **reviews_product** (`id`, `product_id`, `parent_id`, `rating`, `comment`, `created_at`)
- **support_tickets** (`id`, `user_id`, `subject`, `category`, `message`, `status`, `priority`, `assigned_to`, `created_at`)
- **ticket_replies** (`id`, `ticket_id`, `sender_id`, `message`, `is_internal_note`, `created_at`)
- **notifications** (`id`, `user_id`, `type`, `message`, `is_read`, `link`, `created_at`)
- **moderation_log** (`id`, `moderator_id`, `action`, `target_type`, `target_id`, `reason`, `created_at`)
- **role_assignment_log** (`id`, `admin_id`, `user_id`, `old_role`, `new_role`, `reason`, `created_at`)
- **faqs** (`id`, `question`, `answer`, `category`, `status`, `order_index`, `created_at`)

## 🔒 ROW LEVEL SECURITY RULES

- `Parents` *can only read/write their own `bookings`, orders, children, and reviews*
- `Babysitters` *can only read bookings where they are the babysitter_id*
- `Shop owners` can only CRUD their own products and read orders for their products
- `Doctors` can only CRUD their own blog_posts
- `Moderators` can read all products and blog_posts with status='pending', and update their status
- `Support agents` can read/write support_tickets and ticket_replies
- `Admins` have unrestricted access to all tables
- `Public` (unauthenticated): can read products, blog_posts, and babysitter_profiles where status='published' or verified=true


## 📱 RESPONSIVE & UX REQUIREMENTS

- `Fully responsive:` Mobile-first design
- `All dashboards:` collapsible sidebar on mobile (hamburger menu)
- `Loading skeletons on all data-fetch operations`
- `Toast notifications` for all user actions (success, error, warning)
- `Confirmation modals` for destructive actions (ban, delete, cancel booking)
- `Empty state illustrations` for empty tables/lists
- `Pagination on all tables` (10 items per page default)
- `Search` + `filter` on all listing pages
- `404` / `401` /`500` and unauthorized access pages (role tries to access another role's dashboard)

## 📁 FILE & FOLDER STRUCTURE

```
/nanhacare/
│
├── /assets/
│   ├── /css/
│   │   ├── main.css          (global styles, MD3 tokens, 
│   │   │                      typography, color variables)
│   │   ├── components.css    (reusable MD3 components: 
│   │   │                      buttons, cards, chips, 
│   │   │                      fields, dialogs)
│   │   ├── dashboard.css     (sidebar, top bar, 
│   │   │                      dashboard layout)
│   │   └── responsive.css    (media queries, mobile-first)
│   │
│   ├── /js/
│   │   ├── main.js           (global JS: ripple, 
│   │   │                      sidebar toggle, toasts, 
│   │   │                      theme, modals)
│   │   ├── auth.js           (login, register, 
│   │   │                      session check via AJAX)
│   │   ├── dashboard.js      (dashboard interactions)
│   │   ├── babysitters.js    (filter, sort, AJAX fetch)
│   │   ├── marketplace.js    (cart, product filter)
│   │   ├── blog.js           (blog filter, comments)
│   │   └── utils.js          (helpers: format PKR, 
│   │                          date format, skeleton, 
│   │                          pagination)
│   │
│   └── /images/
│       ├── logo.svg
│       ├── hero-bg.jpg
│       ├── baby-footprint.svg
│       └── /placeholders/    (colored gradient placeholder 
│                              images for cards)
│
├── /includes/
│   ├── db.php                (PDO connection, 
│   │                          env config)
│   ├── auth_check.php        (session validation, 
│   │                          role checking function)
│   ├── header.php            (public site header/nav)
│   ├── footer.php            (public site footer)
│   ├── dashboard_header.php  (dashboard top bar)
│   ├── sidebar_admin.php
│   ├── sidebar_moderator.php
│   ├── sidebar_babysitter.php
│   ├── sidebar_parent.php
│   ├── sidebar_shopowner.php
│   ├── sidebar_doctor.php
│   ├── sidebar_support.php
│   └── functions.php         (reusable PHP functions: 
│                              sanitize, format_pkr, 
│                              send_notification, 
│                              generate_badge_id, 
│                              calculate_read_time)
│
├── /api/                     (AJAX endpoints, 
│   │                          return JSON only)
│   ├── login.php
│   ├── register.php
│   ├── logout.php
│   ├── get_babysitters.php
│   ├── get_products.php
│   ├── get_blogs.php
│   ├── submit_booking.php
│   ├── update_booking_status.php
│   ├── add_to_cart.php
│   ├── place_order.php
│   ├── submit_review.php
│   ├── submit_ticket.php
│   ├── get_notifications.php
│   ├── mark_notification_read.php
│   ├── moderate_content.php
│   ├── admin_ban_user.php
│   ├── admin_assign_role.php
│   ├── save_blog_post.php
│   ├── upload_image.php
│   └── get_dashboard_stats.php
│
├── /dashboard/
│   ├── admin/
│   │   ├── index.php         (overview)
│   │   ├── users.php
│   │   ├── roles.php
│   │   ├── moderation.php
│   │   ├── analytics.php
│   │   ├── settings.php
│   │   └── announcements.php
│   ├── moderator/
│   │   ├── index.php
│   │   ├── queue.php
│   │   ├── published.php
│   │   ├── flagged.php
│   │   ├── reports.php
│   │   └── activity.php
│   ├── babysitter/
│   │   ├── index.php
│   │   ├── bookings.php
│   │   ├── profile.php
│   │   ├── earnings.php
│   │   └── reviews.php
│   ├── parent/
│   │   ├── index.php
│   │   ├── bookings.php
│   │   ├── orders.php
│   │   ├── children.php
│   │   ├── saved.php
│   │   ├── bookmarks.php
│   │   └── settings.php
│   ├── shop-owner/
│   │   ├── index.php
│   │   ├── products.php
│   │   ├── add-product.php
│   │   ├── orders.php
│   │   ├── earnings.php
│   │   └── shop-profile.php
│   ├── doctor/
│   │   ├── index.php
│   │   ├── posts.php
│   │   ├── write.php
│   │   ├── comments.php
│   │   ├── profile.php
│   │   └── analytics.php
│   └── support/
│       ├── index.php
│       ├── inbox.php
│       ├── open.php
│       ├── resolved.php
│       ├── faqs.php
│       └── escalations.php
│
├── /public/                  (public-facing pages)
│   ├── babysitters.php
│   ├── babysitter-profile.php
│   ├── marketplace.php
│   ├── product-detail.php
│   ├── blog.php
│   ├── blog-detail.php
│   ├── about.php
│   ├── contact.php
│   ├── pricing.php
│   └── training.php
│
├── index.php                 (home page)
├── login.php
├── register.php
├── verify-email.php
├── forgot-password.php
├── reset-password.php
├── 404.php
├── unauthorized.php
├── cart.php
├── checkout.php
└── .htaccess                 (URL rewrites, 
                               PHP error handling, 
                               security headers)
```