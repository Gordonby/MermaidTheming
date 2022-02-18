# MermaidTheming
Experimenting with mermaid diagram themes

## My main theme

Custom theme overrides using Microsoft Colour Palette

```mermaid
%%{init: 
{
  "theme": "default",
  "themeVariables": {
    "nodeBorder" : "#004990",
    "mainBkg" : "#c9d7e4",
    "actorBkg" : "#01A6F0",
    "signalColor" : "#F34F1C",
    "textColor" : "#747474",
    "loopTextColor" : "#C7C7C7",
    "labelTextColor" : "#C7C7C7",
    "labelBoxBorderColor" : "#7FBC00",
    "labelBoxBkgColor" : "#7FBC00",
    "noteBkgColor" : "#FFBA01",
    "noteBorderColor": "#FFBA01",
    "fontFamily": "Inter",
    "fontSize": "13px"
 }
}
}%%
sequenceDiagram
    participant GitHub Runner
    participant Azure
    participant AKS
    participant MCR
    participant App
    GitHub Runner->>Azure: Login
    Azure-->>GitHub Runner: Token
    GitHub Runner->>AKS: RunCmd: Check for existing install
    Note right of AKS: Conditionally<br/>Force Uninstall
    GitHub Runner->>AKS: RunCmd: Helm Install dry run
    GitHub Runner->>AKS: RunCmd: Helm Install
    AKS->>App: Deploy App
    AKS-->>MCR: Retrieve Container Images
    GitHub Runner->>AKS: RunCmd: Check deployment
    loop WaitForIP
        AKS->>AKS: Wait for IP Address
    end
```

## Mermaid themes

Full list of default Mermaid themes... In the JS https://github.com/mermaid-js/mermaid/blob/b34f7bcdd5ccca50e30efef90de7f2be301000ba/src/themes/index.js
- base
- dark
- default
- forest
- neutral

### Neutral + dark mode

```mermaid
%%{init: {'theme': 'neutral', 'themeVariables': {'darkMode': true}, "flowchart" : { "curve" : "basis" } } }%%
sequenceDiagram
    participant GitHub Runner
    participant Azure
    participant AKS
    participant MCR
    participant App
    GitHub Runner->>Azure: Login
    Azure-->>GitHub Runner: Token
    GitHub Runner->>AKS: RunCmd: Check for existing install
    Note right of AKS: Conditionally<br/>Force Uninstall
    GitHub Runner->>AKS: RunCmd: Helm Install dry run
    GitHub Runner->>AKS: RunCmd: Helm Install
    AKS->>App: Deploy App
    AKS-->>MCR: Retrieve Container Images
    GitHub Runner->>AKS: RunCmd: Check deployment
    loop WaitForIP
        AKS->>AKS: Wait for IP Address
    end
```

### Forest + darkMode

```mermaid
%%{init: {'theme': 'forest', 'themeVariables': {'darkMode': true}, "flowchart" : { "curve" : "basis" } } }%%
sequenceDiagram
    participant GitHub Runner
    participant Azure
    participant AKS
    participant MCR
    participant App
    GitHub Runner->>Azure: Login
    Azure-->>GitHub Runner: Token
    GitHub Runner->>AKS: RunCmd: Check for existing install
    Note right of AKS: Conditionally<br/>Force Uninstall
    GitHub Runner->>AKS: RunCmd: Helm Install dry run
    GitHub Runner->>AKS: RunCmd: Helm Install
    AKS->>App: Deploy App
    AKS-->>MCR: Retrieve Container Images
    GitHub Runner->>AKS: RunCmd: Check deployment
    loop WaitForIP
        AKS->>AKS: Wait for IP Address
    end
```

### Dark theme

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': {'darkMode': true}, "flowchart" : { "curve" : "basis" } } }%%
sequenceDiagram
    participant GitHub Runner
    participant Azure
    participant AKS
    participant MCR
    participant App
    GitHub Runner->>Azure: Login
    Azure-->>GitHub Runner: Token
    GitHub Runner->>AKS: RunCmd: Check for existing install
    Note right of AKS: Conditionally<br/>Force Uninstall
    GitHub Runner->>AKS: RunCmd: Helm Install dry run
    GitHub Runner->>AKS: RunCmd: Helm Install
    AKS->>App: Deploy App
    AKS-->>MCR: Retrieve Container Images
    GitHub Runner->>AKS: RunCmd: Check deployment
    loop WaitForIP
        AKS->>AKS: Wait for IP Address
    end
```

## Fonts

It doesn't seem like the GitHub mermaid markdown rendering supports changing the font family or size

```mermaid
%%{init: 
{
  "theme": "default",
  "themeVariables": {
    "fontFamily": "Inter",
    "fontSize": "25px"
 }
}
}%%
sequenceDiagram
    participant GitHub Runner
    participant Azure
    participant AKS
    participant MCR
    participant App
    GitHub Runner->>Azure: Login
    Azure-->>GitHub Runner: Token
    GitHub Runner->>AKS: RunCmd: Check for existing install
    Note right of AKS: Conditionally<br/>Force Uninstall
    GitHub Runner->>AKS: RunCmd: Helm Install dry run
    GitHub Runner->>AKS: RunCmd: Helm Install
    AKS->>App: Deploy App
    AKS-->>MCR: Retrieve Container Images
    GitHub Runner->>AKS: RunCmd: Check deployment
    loop WaitForIP
        AKS->>AKS: Wait for IP Address
    end
```
