site_name: KG Team Docs
repo_url: https://git.com/KGTeam-Service/docs
theme:
  name: 'material'
  logo: KGTeamDocs/images/icon.png
  features:
    - navigation.sections
    - navigation.top
    - search.highlight
    - toc.follow
  palette:
    - scheme: co
extra_css:
  - stylesheets/co_mkdocs.css
use_directory_urls: false
markdown_extensions:
  - toc:
      title: On This Page
      toc_depth: 2-3
  - attr_list
  - codehilite
  - md_in_html
  - meta
  - abbr
  - pymdownx.betterem
  - pymdownx.blocks.admonition
#     types: ['note', 'warning', 'some-custom-type']
# - pymdownx.blocks.caption
  - pymdownx.blocks.details
  - pymdownx.blocks.html
  - pymdownx.blocks.tab
  - pymdownx.caret
  - pymdownx.details
  - pymdownx.emoji
      # emoji_generator: !!python/name:pymdownx.emoji.to_svg
#  - pymdownx.footnotes
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.progressbar
  - pymdownx.smartsymbols
  - pymdownx.snippets
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
plugins:
  - search
  - mkdocs-video
  - glightbox
extra_javascript:
  - 'https://'
extra:
  captain:
    image: 
  docker:
    image: 

nav:
  - Home: index.md
  - Core Concepts: KGTeamDocs/NewConceptsTools.md
  - Ontology Deep-Dive: KGTeamDocs/ONDeepDive.md
  - Knowledge Graph Deep-Dive: KGTeamDocs/KGDeepDive.md
  - Use Cases: KGTeamServiceDocs/UseCases.md
  - Support: KGTeamDocs/Cargill2030Support.md
  - Team Roles: KGTeamDocs/TeamRoles.md
  - Infrastructure:
    - Architecture: Platform/Architecture.md
    - Tech Stack: Platform/TechStack.md
    - Web Application: Platform/WebApplication.md
  - Projects:
    - ALR: Projects/ALR.md
    - IPM: Projects/IPM.md
  - Onboarding:
    - Team Information: Onboarding/KGTeam/TeamInfo.md
    - Engineering:
      - Team Engineering Sites: Onboarding/KGTeam/Engineering/KGTeamResources/PlatformSites.md
      - Entitlements: Onboarding/KGTeam/Engineering/KGTeamResources/Entitlements.md
      - GitHub:
        - Team Git Repo: Onboarding/KGTeam/Engineering/Git/TeamSite.md
        - Git Strategy: Onboarding/KGTeam/Engineering/Git/GitStrategy.md
      - Resources, Training & Documentation:
        - Core Concepts: Onboarding/KGTeam/Engineering/TechnologyResources/Concepts.md
        - Tools & Technology: Onboarding/KGTeam/Engineering/TechnologyResources/ToolsTechnology.md
        - Programming & Query Languages: Onboarding/KGTeam/Engineering/TechnologyResources/ProgrammingLanguages.md
    - Graph Projects:
      - Project Implementation Workflow: Onboarding/Projects/ProjectProcess.md
