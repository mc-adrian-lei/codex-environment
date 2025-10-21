# Codex Environment

Codex meta-environment for research-driven UI framework and modular workflow automation. Mirrors, manages, and extends feature development for Cognitive Mapping and Mind–Body–Energy Systems.

## Purpose

This repository serves as the **meta-development environment** for building, managing, and extending research-driven UI frameworks. It provides:

- **Clean separation of concerns**: Development tools and meta-framework separate from the main research/UI application
- **Modular workflow automation**: Streamlined tools for component development, Git automation, and template management
- **Direct integration**: Seamless linking between Codex meta-framework and primary research applications

## Main Project Links

### Primary Research/UI Repository
- **Repository**: [mc-adrian-lei-github.io](https://github.com/mc-adrian-lei/mc-adrian-lei-github.io)
- **Live Deployment**: [https://mc-adrian-lei.github.io/mc-adrian-lei-github.io/](https://mc-adrian-lei.github.io/mc-adrian-lei-github.io/)

### Related Resources
- **Codex ChatGPT Interface**: [https://chatgpt.com/codex](https://chatgpt.com/codex)

## Project Structure

```
codex-environment/
├── src/
│   ├── components/          # Reusable UI components
│   │   ├── library/         # Component library sidebar
│   │   ├── timeline/        # Timeline/history panel
│   │   └── documentation/   # Integrated documentation panel
│   ├── automation/          # GitHub/PR automation tools
│   │   ├── git-helpers.js   # Git workflow automation
│   │   └── pr-manager.js    # Pull request management
│   ├── templates/           # Template-driven prompts
│   │   ├── component-templates/
│   │   └── workflow-templates/
│   └── index.html           # Main Codex interface
├── public/                  # Static assets
├── docs/                    # Documentation
└── README.md
```

## Meta-Features Roadmap

### Phase 1: Foundation
- [x] Repository initialization
- [x] Basic structure setup
- [ ] Component Library Sidebar
- [ ] Base web app interface

### Phase 2: Automation
- [ ] GitHub/PR automation integration
- [ ] Template-driven prompt system
- [ ] Direct repo linking functionality
- [ ] Quick-launch to GitHub Pages

### Phase 3: Advanced Features
- [ ] Timeline/history panel
- [ ] Integrated documentation panel
- [ ] Real-time sync with main UI repo
- [ ] Feature branch management

### Phase 4: Enhancement
- [ ] Advanced component library
- [ ] Workflow optimization tools
- [ ] Testing framework integration
- [ ] Deployment automation

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/mc-adrian-lei/codex-environment.git

# Navigate to project directory
cd codex-environment

# Install dependencies
npm install

# Start development server
npm start
```

### Linking to Main Project

The Codex environment is designed to work seamlessly with the main research UI repository. Configure the link in your local environment:

```javascript
// config.js
module.exports = {
  mainRepo: 'https://github.com/mc-adrian-lei/mc-adrian-lei-github.io',
  liveDeployment: 'https://mc-adrian-lei.github.io/mc-adrian-lei-github.io/',
  codexInterface: 'https://chatgpt.com/codex'
};
```

## Development Workflow

1. **Develop in Codex**: Use this environment to create and test new components
2. **Test Locally**: Verify functionality within Codex interface
3. **Push to Main**: Export/link changes to main UI research repo
4. **Create PRs**: Automated PR creation for feature branches
5. **Deploy**: Test on GitHub Pages live instance

## Contributing

This is a personal meta-development environment for research-driven UI framework development. The repository structure and tools are designed to support the Cognitive Mapping and Mind–Body–Energy Systems research project.

## Research Focus Areas

- **Cognitive Mapping**: Visual representation and navigation of cognitive processes
- **Mind–Body–Energy Systems**: Integrated framework for understanding human energy dynamics
- **32 Aspect Dev Self Clock**: Primary research application and UI implementation

## License

This project is part of ongoing research. All rights reserved.

## Contact

For questions or collaboration inquiries related to this meta-development environment, please open an issue in this repository or contact through the main project repository.

---

**Last Updated**: October 21, 2025
