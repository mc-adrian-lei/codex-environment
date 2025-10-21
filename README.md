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

## GitHub Actions Workflow Integration

### Overview
The `extract-adapt-add.yml` workflow automates content synchronization and artifact processing from external sources into this repository.

### Workflow Triggers
The workflow is configured with two trigger mechanisms:

1. **repository_dispatch** (External API trigger)
   - Event type: `codex extract-adapt-add`
   - Ideal for custom GPT, external services, or content repositories
   - Requires GitHub Personal Access Token (PAT)

2. **workflow_dispatch** (Manual trigger)
   - Can be manually triggered from GitHub Actions UI
   - Useful for testing and on-demand execution

### Triggering from External Sources

#### Using repository_dispatch with cURL:
```bash
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer YOUR_GITHUB_PAT" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/mc-adrian-lei/codex-environment/dispatches \
  -d '{"event_type":"codex extract-adapt-add","client_payload":{"source":"external","description":"Content sync from custom GPT"}}'
```

#### Using repository_dispatch from Custom GPT:
Configure your custom GPT to make POST requests to:
```
https://api.github.com/repos/mc-adrian-lei/codex-environment/dispatches
```

With headers:
```json
{
  "Accept": "application/vnd.github+json",
  "Authorization": "Bearer YOUR_GITHUB_PAT",
  "X-GitHub-Api-Version": "2022-11-28"
}
```

With body:
```json
{
  "event_type": "codex extract-adapt-add",
  "client_payload": {
    "source": "custom-gpt",
    "description": "Automated content extraction"
  }
}
```

### Setting Up Personal Access Token (PAT)

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Set scopes: `repo` (full control of private repositories)
4. Copy the generated token
5. Store securely and use in Authorization header

### Workflow Process

The `extract-adapt-add.yml` workflow performs the following steps:

1. **Checkout Repository**: Clones the current repository state
2. **Scan for Artifacts**: Looks for markdown files, JSON data, or other artifacts to process
3. **Adapt & Format**: Processes and formats content according to project structure
4. **Commit & Push**: Automatically commits changes with descriptive messages

### Content Synchronization

The workflow is designed to:
- Extract content from external sources
- Adapt formatting to match repository conventions
- Add processed content to appropriate directories
- Maintain version history through Git commits

### Webhook Alternative

If you prefer webhooks over repository_dispatch:
1. Navigate to Settings → Webhooks → Add webhook
2. Set Payload URL to your service endpoint
3. Configure events: Choose "Let me select individual events"
4. Select relevant events (e.g., push, pull_request)
5. Set Content type: application/json
6. Add webhook secret for security

**Note**: Webhooks are triggered by GitHub events, while repository_dispatch is triggered by external API calls.

### Monitoring Workflow Execution

- View workflow runs: [Actions Tab](https://github.com/mc-adrian-lei/codex-environment/actions)
- Check workflow logs for debugging
- Monitor commit history for automated changes

## Meta-Features Roadmap
### Phase 1: Foundation
- [x] Repository initialization
- [x] Basic structure setup
- [x] GitHub Actions workflow configuration
- [ ] Component Library Sidebar
- [ ] Base web app interface

### Phase 2: Automation
- [x] GitHub Actions extract-adapt-add workflow
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

## Contributing
Contributions are welcome! Please read our contributing guidelines before submitting pull requests.

## License
MIT License - See LICENSE file for details
