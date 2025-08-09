# Unraid Community Applications Templates

A curated collection of **production-ready** Docker container templates for Unraid Community Applications.

## 🎯 **Project Mission**

This repository provides **high-quality, secure, and well-documented** templates for self-hosted applications on Unraid. Our focus is on delivering templates that follow security best practices, provide comprehensive documentation, and offer a superior user experience.

### **Why This Repository?**

- **🔒 Security First**: Non-privileged containers, proper permissions, secure defaults
- **📖 Comprehensive Documentation**: Detailed setup guides, troubleshooting, and best practices  
- **🚀 Production Ready**: Tested configurations used in real-world deployments
- **🤝 Community Driven**: Open source with transparent development and contribution process
- **⚡ Modern Automation**: GitHub Actions for validation, testing, and quality assurance

---

## 📦 **Available Templates**

### 💼 **Productivity & Cloud Storage**
| Application | Description | Status |
|-------------|-------------|--------|
| [**OwnCloud OCIS**](./templates/Productivity/owncloud-ocis/) | Modern cloud storage platform with microservices architecture | ✅ Available |

### 🎬 **Media Management (Arr Suite)**
| Application | Description | Status |
|-------------|-------------|--------|
| **Sonarr** | TV series management and automation | 🔄 Coming Soon |
| **Radarr** | Movie collection management and automation | 🔄 Coming Soon |
| **Prowlarr** | Indexer manager for *arr applications | 🔄 Coming Soon |
| **Readarr** | Book collection management and automation | 🔄 Coming Soon |

### 📺 **Media Servers**
| Application | Description | Status |
|-------------|-------------|--------|
| **Plex** | Feature-rich media server with premium features | 🔄 Coming Soon |
| **Jellyfin** | Open-source alternative to Plex | 🔄 Coming Soon |

### ⬇️ **Download Clients**
| Application | Description | Status |
|-------------|-------------|--------|
| **qBittorrent** | Lightweight, feature-rich BitTorrent client | 🔄 Coming Soon |
| **SABnzbd** | Usenet binary downloader | 🔄 Coming Soon |

### 📊 **Monitoring & Management**
| Application | Description | Status |
|-------------|-------------|--------|
| **Overseerr** | Request management for media libraries | 🔄 Coming Soon |

*Legend: ✅ Available | 🔄 Coming Soon | 🚧 In Development*

---

## 🚀 **Quick Start**

### **For Template Users**

1. **Browse Available Templates**
   ```bash
   # View all available templates
   ls templates/
   ```

2. **Install via Community Applications**
   - Open Unraid WebGUI → Apps tab
   - Search for the application name
   - Look for "Beacon Tech Consulting" templates
   - Click Install and configure

3. **Manual Installation**
   ```bash
   # Download template XML
   wget https://raw.githubusercontent.com/beacontechconsulting/Unraid_CA_Templates/main/templates/Category/app/app.xml
   
   # Import via Unraid Docker settings
   # Docker → Add Container → Template: [Select downloaded XML]
   ```

### **For Contributors**

1. **Clone Repository**
   ```bash
   git clone https://github.com/beacontechconsulting/Unraid_CA_Templates.git
   cd Unraid_CA_Templates
   ```

2. **Set Up Development Environment**
   ```bash
   # Install dependencies
   yarn install
   
   # Validate existing templates
   yarn validate
   ```

3. **Create New Template**
   ```bash
   # Follow template guidelines
   mkdir -p templates/Category/app-name
   # Create app-name.xml, icon.png, README.md
   
   # Test your template
   yarn test:template templates/Category/app-name/app-name.xml
   ```

4. **Submit Changes**
   ```bash
   git checkout -b feature/new-template
   git add templates/Category/app-name/
   git commit -m "feat: add AppName template"
   git push origin feature/new-template
   # Create Pull Request on GitHub
   ```

---

## 🛠 **Development & Testing**

### **Prerequisites**
- **Node.js** 18+ and **Yarn**
- **Docker** and **Docker Compose** (for testing)
- **Git** for version control

### **Available Scripts**
```bash
# Validation
yarn validate              # Validate all templates
yarn validate:template     # Validate specific template
yarn test:template <file>  # Test single template

# Documentation
yarn docs:generate         # Generate template documentation
yarn docs:serve           # Serve documentation locally

# Icon Management
yarn icons:fetch          # Download missing icons
yarn icons:validate       # Validate icon specifications

# Quality Assurance
yarn lint                 # Lint JavaScript/TypeScript files
yarn lint:fix             # Auto-fix linting issues
```

### **Template Testing Workflow**
```bash
# 1. Create your template
cp templates/Productivity/owncloud-ocis/owncloud-ocis.xml templates/Category/new-app/new-app.xml

# 2. Validate XML structure
yarn validate:template templates/Category/new-app/new-app.xml

# 3. Test with Docker Compose
cd templates/Category/new-app/
cp docker-compose.example.yml docker-compose.yml
# Edit configuration as needed
docker-compose up -d

# 4. Verify functionality
curl -I http://localhost:PORT
docker-compose logs -f

# 5. Clean up test environment
docker-compose down -v
```

---

## 📋 **Template Standards**

All templates in this repository adhere to **strict quality standards**:

### **✅ Required Standards**
- **Valid XML Structure** - Passes automated validation
- **Security Hardening** - Non-root user, minimal permissions
- **Consistent Configuration** - Standardized paths and variables
- **Comprehensive Documentation** - Setup guides and troubleshooting
- **Icon Specifications** - 64x64 PNG with proper branding
- **Testing Verification** - Tested on real Unraid systems

### **📚 Documentation Requirements**
- **Template XML** with proper metadata and descriptions
- **README.md** with setup instructions and troubleshooting
- **Docker Compose Example** for local testing
- **Icon** following CA specifications

### **🔒 Security Requirements**
- Containers run as **non-privileged** unless absolutely necessary
- **PUID/PGID** support for proper file permissions
- **Secure defaults** for all configuration options
- **Security warnings** for sensitive configurations

See our detailed [**Template Guidelines**](./docs/TEMPLATE_GUIDELINES.md) for complete requirements.

---

## 🤝 **Contributing**

We welcome contributions from the community! Whether you're:

- **🆕 Adding new templates** for applications not yet covered
- **🔧 Improving existing templates** with better configurations
- **🐛 Fixing bugs** or updating documentation
- **💡 Suggesting features** or enhancements

### **Contribution Process**

1. **Check Existing Issues** - Look for existing requests or bug reports
2. **Follow Guidelines** - Read our [Contributing Guide](./docs/CONTRIBUTING.md)
3. **Create Quality Templates** - Follow our [Template Guidelines](./docs/TEMPLATE_GUIDELINES.md)
4. **Test Thoroughly** - Validate and test your templates
5. **Submit Pull Request** - Include detailed description and testing notes

### **Template Requests**
Need a template for an application not listed? [**Open an issue**](https://github.com/beacontechconsulting/Unraid_CA_Templates/issues/new?template=template_request.md) with details about:
- Application name and description
- Official Docker image or repository
- Key configuration requirements
- Use case and benefits

### **Code of Conduct**
This project follows the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/). Be respectful, inclusive, and constructive in all interactions.

---

## 📄 **License**

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### **What This Means**
- ✅ **Free to use** for personal and commercial projects
- ✅ **Modify and distribute** with attribution
- ✅ **No warranty** - use at your own risk
- ✅ **Attribution required** - credit Beacon Tech Consulting

---

## 🙏 **Acknowledgments**

### **Community & Inspiration**
- **[Unraid Community](https://unraid.net/)** - For creating an amazing platform
- **[LinuxServer.io](https://linuxserver.io/)** - For maintaining excellent Docker images
- **[TRaSH Guides](https://trash-guides.info/)** - For quality profiles and best practices
- **[Community Applications](https://github.com/Squidly271/community.applications)** - For the plugin ecosystem

### **Tools & Technologies**
- **[GitHub Actions](https://github.com/features/actions)** - For CI/CD automation
- **[Docker](https://docker.com/)** - For containerization

---

## 📞 **Support & Community**

### **Getting Help**
- **📖 Documentation**: Check template-specific README files
- **🐛 Bug Reports**: [GitHub Issues](https://github.com/stephondoestech/Unraid_CA_Templates/issues)
- **💬 Questions**: [GitHub Discussions](https://github.com/stephondoestech/Unraid_CA_Templates/discussions)
- **🚀 Feature Requests**: [GitHub Issues](https://github.com/stephondoestech/Unraid_CA_Templates/issues/new?template=feature_request.md)

### **Community Resources**
- **[Unraid Forums](https://forums.unraid.net/)** - Official community support
- **[r/unRAID](https://reddit.com/r/unRAID)** - Reddit community
- **[Unraid Discord](https://discord.gg/unraid)** - Real-time chat support

### **Professional Services**
Need help with custom Unraid templates or infrastructure? Professional consulting services are available for:
- Custom template development
- Unraid system optimization  
- Infrastructure automation
- Security hardening

---

## 📊 **Project Stats**

![GitHub stars](https://img.shields.io/github/stars/stephondoestech/Unraid_CA_Templates?style=social)
![GitHub forks](https://img.shields.io/github/forks/stephondoestech/Unraid_CA_Templates?style=social)
![GitHub issues](https://img.shields.io/github/issues/stephondoestech/Unraid_CA_Templates)
![GitHub pull requests](https://img.shields.io/github/issues-pr/stephondoestech/Unraid_CA_Templates)

**Built with ❤️ for the Unraid community**

---

*Last updated: August 2025*
