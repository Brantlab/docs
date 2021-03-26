# Homer
- [home.brantlab.com](https://home.brantlab.com)
## Why do I run this? 
Homer is a static genrated webpage based off YML file to generate the content on the page. This make a very easy dashboard to access services and easy to remember what I have. 

## My install
1. I made a directory for the needed data to live in. 
    
    ```
    mkdir homer
    ```

2. Changed to the directory to run my docker commands
    
    ```
    cd homer
    ```

3. Ran the docker command being sure to set the path where the assets will exist.

    ```
    docker run -d \
        -p 8080:8080 \
        -v <directory>:/www/assets \
        --restart=always \
        b4bz/homer:latest
    ```

    This is an example of what I ran but yours may be a bit different.

    ```
    docker run -d \
        -p 8080:8080 \
        -v /home/docker/homer:/www/assets \
        --restart=always \
        b4bz/homer:latest
    ```

4. Go to your IP address for docker host like so http://172.16.10.19:8080

## My customizations so far

- Link to the page https://home.brantlab.com 
- Note that some links may not work because they are not public
- `config.yml`
``` yml
---
# Homepage configuration
# See https://fontawesome.com/icons for icons options

title: "BrantLab"
subtitle: "Intranet"
logo: "assets/icons/logo_brantlab.png"
# icon: "fas fa-skull-crossbones" # Optional icon

header: true
footer: "Brantlab.com"

columns: "3" # "auto" or number (must be a factor of 12: 1, 2, 3, 4, 6, 12)
connectivityCheck: true # whether you want to display a message when the apps are not accessible anymore (VPN disconnected for example)

# Optional theme customization
theme: dark
colors:
#  light:
#    highlight-primary: "#3367d6"
#    highlight-secondary: "#4285f4"
#    highlight-hover: "#5a95f5"
#    background: "#f5f5f5"
#    card-background: "#ffffff"
#    text: "#363636"
#    text-header: "#ffffff"
#    text-title: "#303030"
#    text-subtitle: "#424242"
#    card-shadow: rgba(0, 0, 0, 0.1)
#    link-hover: "#363636"
  dark:
    highlight-primary: "#2b2b2b"
    highlight-secondary: "#131313"
    highlight-hover: "#ff0000"
    background: "#131313"
    card-background: "#2b2b2b"
    text: "#eaeaea"
    text-header: "#f5f5f5"
    text-title: "#fafafa"
    text-subtitle: "#f5f5f5"
    card-shadow: rgba(0, 0, 0, 0.2)
    link-hover: "#ffdd57"

# Optional message
message:
  #url: https://b4bz.io
  style: "is-dark" # See https://bulma.io/documentation/components/message/#colors for styling options.
  title: "Common Information for home network"
  content: "Subnet: 172.16.10.0/24 <br/> Gateway: 172.16.10.1"

# Optional navbar
# links: [] # Allows for navbar (dark mode, layout, and search) without any links
links:
  - name: "vCenter"
    icon: "fas fa-server"
    url: "https://vcsa.brantlab.com"
    target: "_blank" # optional html a tag target attribute
  - name: "Wiki"
    icon: "fas fa-book"
    url: "https://www.wikipedia.org/"
  # this will link to a second homer page that will load config from additionnal-page.yml and keep default config values as in config.yml file
  # see url field and assets/additionnal-page.yml.dist used in this example:
  - name: "another page!"
    icon: "fas fa-file-alt"
    url: "#sample" 

# Services
# First level array represent a group.
# Leave only a "items" key if not using group (group name, icon & tagstyle are optional, section separation will not be displayed).
services:
  - name: "Websites"
    icon: "fas fa-cloud"
    items:
      - name: "Reddit Self-Hosted"
        logo: "https://styles.redditmedia.com/t5_32hch/styles/communityIcon_b2t5inv46z331.png?width=256&s=5d284561c13dd03558bf82907d5c7438b0eba1f6"
        subtitle: "a place of goodness"
        url: "https://www.reddit.com/r/selfhosted/"
        target: "_blank" # optional html a tag target attribute
      - name: "Remote Access Console (RAC)"
        icon: "fas fa-desktop"
        subtitle: "Remote Access for internet based systems"
        url: "https://rac.grunetworks.xyz/"
        target: "_blank" # optional html a tag target attribute
      - name: "GitHub"
        logo: "https://image.flaticon.com/icons/png/512/25/25231.png"
        subtitle: "Online Repo"
        url: "https://github.com/Brantlab"
        target: "_blank" # optional html a tag target attribute
      - name: "Google Domains"
        logo: "https://cdn.freelogovectors.net/wp-content/uploads/2020/11/google-domains-logo.png"
        subtitle: "The Best Registrar?"
        url: "https://domains.google.com"
        target: "_blank" # optional html a tag target attribute

  - name: "HomeLab Apps"
    icon: "fas fa-beer"
    items:
      - name: "Code"
        subtitle: "VS Code Browser"
        url: "http://code.brantlab.com"
        logo: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/1200px-Visual_Studio_Code_1.35_icon.svg.png"
        target: "_blank" # optional html a tag target attribute
      - name: "Unifi Controller"
        subtitle: "Unifi home controller"
        logo: "https://cdn.iconscout.com/icon/free/png-512/ubiquiti-2752044-2284861.png"
        url: "https://unifi.brantlab.com:8443"
        target: "_blank" # optional html a tag target attribute
      - name: "Nginx Proxy"
        subtitle: "Nginx Proxy Manager in docker"
        logo: "https://img.icons8.com/color/452/nginx.png"
        url: "http://proxy.brantlab.com"
        target: "_blank" # optional html a tag target attribute
      - name: "IPAM"
        subtitle: "PHP IPAM"
        logo: "https://pbs.twimg.com/profile_images/817486869147635712/p6CxwSmh_400x400.png"
        url: "https://ipam.brantlab.com"
        target: "_blank" # optional html a tag target attribute
      - name: "PI Hole"
        subtitle: "Block All The Things"
        logo: "https://upload.wikimedia.org/wikipedia/commons/0/00/Pi-hole_Logo.png"
        url: "http://172.16.10.9/admin"
        type: "PiHole" 
        target: "_blank" # optional html a tag target attribute
      - name: "Local Mesh Central"
        subtitle: "For Home use"
        logo: "https://png.pngitem.com/pimgs/s/15-151888_connecting-dots-sphere-png-connection-png-transparent-png.png"
        url: "http://dc.brantlab.com"
        target: "_blank" # optional html a tag target attribute

  - name: "Physical Components"
    icon: "fas fa-server"
    items:
      - name: "VCSA"
        subtitle: "VCSA 6.7 U1"
        logo: "https://www.definit.co.uk/images/2014/07/vSphereLogo.png"
        url: "https://vcsa.brantlab.com"
        target: "_blank" # optional html a tag target attribute
      - name: "ESXI Host"
        subtitle: "Single Host"
        logo: "https://cdn.iconscout.com/icon/free/png-512/vmware-3-569535.png"
        url: "http://172.16.10.20"
        target: "_blank" # optional html a tag target attribute
      - name: "Synology"
        subtitle: "NAS"
        #logo: "https://cdn.iconscout.com/icon/free/png-512/vmware-3-569535.png"
        icon: "fab fa-fort-awesome-alt"
        url: "http://synology.brantlab.com"
        target: "_blank" # optional html a tag target attribute
      - name: "Printer"
        subtitle: "Yuck"
        #logo: "https://cdn.iconscout.com/icon/free/png-512/vmware-3-569535.png"
        #icon: "fab fa-fort-awesome-alt"
        url: "http://172.16.10.51"
        target: "_blank" # optional html a tag target attribute
```