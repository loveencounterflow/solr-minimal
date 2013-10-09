




## Solr Minimal: A <small>(not quite as yet)</small> Minimalist Solr Distro

### Installation

First, do

    git clone https://github.com/loveencounterflow/solr-minimal.git

gives a you a directory `solr-minimal` in your current directory. Rename it or move it if you want to; the
following has to be read accordingly.

There's a daemon script `solr-minimal/etc-init.de/solr`; if you are on a typical Linux bos,
that script should appear as `/etc/init.d/solr`, so make a link:

    cd /etc/init.d
    ln -s /path/to/solr-minimal/etc-init.de/solr solr
    cd -

These steps must be done as root or using `sudo`, as you like.

Then, open `/etc/init.d/solr` (which should work if the link is correct), and head for line 16:

    daemon --chdir='/path/to/solr-minimal/example' --command "java -jar start.jar" --respawn --output=/var/log/solr/solr.log --name=solr --verbose

Adjust that first path, and, if you like to, the second one, too.

One last consideration: your Solr instance is configured with

    /path/to/solr-minimal/example/solr/collection1/conf/solrconfig.xml
    /path/to/solr-minimal/example/solr/collection1/conf/schema.xml

which is also where your data lives.


