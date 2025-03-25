# iwslt.org

Website for the IWSLT conference using an adaptation of the [Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes).

Small single-page edits may be made directly in github.com (please be sure to preview first).  
For larger edits which span multiple pages, consider making changes on your local machine; these should be previewed to test before pushing to the site as below.


## Installing ruby to preview local changes

Previewing the site uses ruby + jekyll. If you have an M1 Mac, see [here](https://github.com/danielfrance/Installing-Ruby-On-M1-Macs/) to install ruby. 

Use Homebrew to install ruby 3.4.2 and then jekyll:
```shell
brew update
brew install rbenv ruby-build

rbenv init
rbenv install rbenv install 3.4.2
rbenv global 3.4.2

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc

source ~/.bashrc
gem install jekyll
```
Then, navigate to `iwslt.github.io` and run `bundle install` to install required Ruby gems for the project. 


### Previewing the site

Once the above has been done successfully, you should be able to make changes locally and run 
```shell
bundle exec jekyll serve
```
to preview local changes on http://127.0.0.1:4000. 


---

### Additional information for Jekyll sites on GitHub Pages:

- [Setting up a Jekyll site with GitHub Pages](https://jekyllrb.com/docs/github-pages/)
- [Configuring GitHub Metadata](https://github.com/jekyll/github-metadata/blob/master/docs/configuration.md#configuration) to work properly when developing locally and avoid `No GitHub API authentication could be found. Some fields may be missing or have incorrect data.` warnings.
