# Text & Diagrams
## [Typora](https://typora.io/)
* Releases: https://typora.io/releases/all
```bash
# add Typora's key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://downloads.typora.io/typora.gpg | sudo tee /etc/apt/keyrings/typora.gpg > /dev/null
# add Typora's repository securely
echo "deb [signed-by=/etc/apt/keyrings/typora.gpg] https://downloads.typora.io/linux ./" | sudo tee /etc/apt/sources.list.d/typora.list
sudo apt update
# install typora
sudo apt install typora
```
## Draw io

* Repository: https://github.com/jgraph/drawio-desktop/
* Releases: https://github.com/jgraph/drawio-desktop/releases
* Deb file: https://github.com/jgraph/drawio-desktop/releases/download/v29.6.6/drawio-amd64-29.6.6.deb

## Scribus
https://www.scribus.net/contribute/

## MasterPDF Editor
https://code-industry.net/free-pdf-editor/#get

```bash
curl -s http://repo.code-industry.net/deb/pubmpekey.asc | sudo tee /usr/share/keyrings/pubmpekey.asc
echo -e "Types: deb
Architectures: amd64
URIs: http://repo.code-industry.net/deb
Suites: stable
Components: main
Signed-By: /usr/share/keyrings/pubmpekey.asc" | sudo tee /etc/apt/sources.list.d/master-pdf-editor.sources
sudo apt update
sudo apt install master-pdf-editor-5
```
## Eloquent
https://flathub.org/en/apps/re.sonny.Eloquent
```bash
flatpak install flathub re.sonny.Eloquent
```
Run
```bash
flatpak run re.sonny.Eloquent
```

## PDF4QT
* https://github.com/JakubMelka/PDF4QT

  
