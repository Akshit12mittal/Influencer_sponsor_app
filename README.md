# Brand Booster - Influencer & Sponsor Platform

**Brand Booster** is a dynamic web platform that bridges the gap between sponsors and influencers, enabling seamless collaboration for marketing campaigns. The platform provides a comprehensive solution for brands to expand their reach and influencers to find impactful collaboration opportunities.

## ✨ Features

### For Sponsors
- **Company Profile Management** - Create and manage company profiles with industry details
- **Campaign Creation** - Launch marketing campaigns with specific goals, budgets, and timelines
- **Campaign Management** - Edit, activate/deactivate, and delete campaigns
- **Visibility Control** - Set campaigns as public (visible to all) or private (invitation-only)
- **Influencer Discovery** - Search and browse influencer profiles

### For Influencers
- **Profile Creation** - Showcase your niche, platform, and follower count
- **Campaign Discovery** - Browse active public campaigns
- **Campaign Responses** - Accept or reject campaign offers
- **Request Tracking** - Monitor campaign request status

### For Administrators
- **Comprehensive Dashboard** - View platform statistics and analytics
- **User Management** - Monitor active influencers and sponsors
- **Campaign Oversight** - Track all campaigns (public/private)
- **Request Monitoring** - View pending, accepted, and rejected campaign requests
- **Platform Analytics** - Visual charts showing campaign distribution and request status
- **Content Moderation** - Flag and review problematic users

### General Features
- **Secure Authentication** - Role-based login system (Admin, Sponsor, Influencer)
- **Responsive Design** - Dark-themed, modern UI with Bootstrap 5
- **Search Functionality** - Find influencers, sponsors, and campaigns
- **Real-time Updates** - Track campaign status changes
- **Database Integration** - SQLite database with SQLAlchemy ORM

## 🛠️ Tech Stack

### Backend
- **Flask 3.0.3** - Python web framework
- **SQLAlchemy 2.0.32** - ORM for database operations
- **Flask-Migrate 4.1.0** - Database migrations
- **Python-dotenv 1.0.1** - Environment variable management

### Frontend
- **Bootstrap 5.3.2** - Responsive CSS framework
- **Font Awesome 6.4.0** - Icon library
- **Chart.js** - Data visualization for admin dashboard
- **Jinja2 3.1.4** - Template engine

### Database
- **SQLite** - Lightweight relational database

## 👥 User Roles

### 1. Admin
- **Access Level:** Highest
- **Capabilities:**
  - View comprehensive platform statistics
  - Monitor all users and campaigns
  - Access admin-only dashboard
  - Flag problematic content/users
  - Full search access

### 2. Sponsor
- **Access Level:** Medium
- **Capabilities:**
  - Create and manage campaigns
  - Search for influencers
  - View campaign requests
  - Edit company profile
  - Control campaign visibility

### 3. Influencer
- **Access Level:** Standard
- **Capabilities:**
  - View and respond to campaigns
  - Manage profile information
  - Search for campaigns and sponsors
  - Track request history
  - Accept/reject campaign offers

## 🛣️ API Routes

### Authentication Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/` | Login page |
| POST | `/login` | User authentication |
| GET | `/logout` | User logout |

### Registration Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/influencer_register` | Influencer registration form |
| POST | `/submit_influencer_registration` | Submit influencer registration |
| GET | `/sponsor_register` | Sponsor registration form |
| POST | `/submit_sponsor_registration` | Submit sponsor registration |

### Dashboard Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/influencer_dashboard` | Influencer dashboard |
| GET | `/sponsor_dashboard` | Sponsor dashboard |
| GET | `/admin_dashboard` | Admin dashboard |

### Campaign Management Routes
| Method | Route | Description |
|--------|-------|-------------|
| POST | `/create_campaign` | Create new campaign |
| GET/POST | `/edit_campaign/<id>` | Edit campaign |
| POST | `/delete_campaign/<id>` | Delete campaign |
| POST | `/activate_campaign/<id>` | Activate campaign |
| POST | `/deactivate_campaign/<id>` | Deactivate campaign |
| POST | `/respond_campaign/<id>` | Accept/reject campaign |

### Search Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/find` | Search interface |
| POST | `/search_influencers` | Search influencers |
| POST | `/search_campaigns` | Search campaigns |
| POST | `/search_sponsors` | Search sponsors |

## 🎯 Database Schema

### User_entry Table
- `id` (String, Primary Key)
- `username` (String, Unique)
- `password` (String) - **Should be hashed**
- `role` (String) - admin/sponsor/influencer

### Influencer Table
- `id` (Integer, Primary Key)
- `username` (String, Unique)
- `email` (String, Unique)
- `niche` (String)
- `platform` (String)
- `followers` (Integer)
- `password` (String)

### Sponsor Table
- `id` (Integer, Primary Key)
- `company_name` (String)
- `industry` (String)
- `budget` (Float)
- `email` (String, Unique)
- `password` (String)

### Campaign Table
- `id` (Integer, Primary Key)
- `sponsor_id` (Integer)
- `name` (String)
- `description` (String)
- `start_date` (Date)
- `end_date` (Date)
- `budget` (Float)
- `visibility` (String) - public/private
- `goals` (String)
- `status` (Boolean)

### CampaignRequest Table
- `id` (Integer, Primary Key)
- `campaign_id` (Integer)
- `sponsor_id` (Integer)
- `influencer_id` (Integer)
- `status` (Integer) - 0=pending, 1=accepted, 2=rejected
- `date_of_request` (DateTime)
- `date_of_modification` (DateTime)

## 🙏 Acknowledgments

- Bootstrap team for the excellent CSS framework
- Font Awesome for comprehensive icon library
- Flask community for extensive documentation
- Chart.js for beautiful data visualization

## 📚 Additional Resources

- [Flask Documentation](https://flask.palletsprojects.com/)
- [SQLAlchemy Documentation](https://docs.sqlalchemy.org/)
- [Bootstrap Documentation](https://getbootstrap.com/docs/5.3/)
- [Chart.js Documentation](https://www.chartjs.org/docs/latest/)

---

**Built with ❤️ for connecting brands and influencers**
