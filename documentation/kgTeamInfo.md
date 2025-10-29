site_name: Metadata Service Docs
repo_url: https://git.cglcloud.com/Metadata-Service/mds-docs
theme:
  name: 'material'
  logo: MetadataServiceDocs/images/mds_icon.png
  features:
    - navigation.sections
    - navigation.top
    - search.highlight
    - toc.follow
  palette:
    - scheme: cargill
extra_css:
  - stylesheets/cargill_mkdocs.css
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
  - 'https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-MML-AM_CHTML'
extra:
  captain:
    image: cglclouddev-cglclouddev-docker-utilities.jfrog.io/captain:1-stable
  docker:
    image: cglclouddev-cglclouddev-docker-utilities.jfrog.io/drone-plugin-cgl-docker:3-stable

nav:
  - Home: index.md
  - Core Concepts: MetadataServiceDocs/NewConceptsTools.md
  - Ontology Deep-Dive: MetadataServiceDocs/ONDeepDive.md
  - Knowledge Graph Deep-Dive: MetadataServiceDocs/KGDeepDive.md
  - Use Cases: MetadataServiceDocs/UseCases.md
  - Cargill 2030 Support: MetadataServiceDocs/Cargill2030Support.md
  - Team Roles: MetadataServiceDocs/TeamRoles.md
  - Infrastructure:
    - Architecture: Platform/Architecture.md
    - Tech Stack: Platform/TechStack.md
    - Web Application: Platform/WebApplication.md
  - Projects:
    - ANH Lifecycle Assessment Repository: Projects/ALR.md
    - ANH Integration Profiling & Management: Projects/IPM.md
  - Onboarding:
    - Team Information: Onboarding/MDSTeam/TeamInfo.md
    - Engineering:
      - Team Engineering Sites: Onboarding/MDSTeam/Engineering/MDSPlatformResources/PlatformSites.md
      - Entitlements: Onboarding/MDSTeam/Engineering/MDSPlatformResources/Entitlements.md
      - GitHub:
        - Team Git Repo: Onboarding/MDSTeam/Engineering/Git/TeamSite.md
        - Git Strategy: Onboarding/MDSTeam/Engineering/Git/GitStrategy.md
      - Resources, Training & Documentation:
        - Core Concepts: Onboarding/MDSTeam/Engineering/TechnologyResources/Concepts.md
        - Tools & Technology: Onboarding/MDSTeam/Engineering/TechnologyResources/ToolsTechnology.md
        - Programming & Query Languages: Onboarding/MDSTeam/Engineering/TechnologyResources/ProgrammingLanguages.md
    - Graph Projects:
      - Project Implementation Workflow: Onboarding/Projects/ProjectProcess.md
