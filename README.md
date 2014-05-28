# Vagrantfiles #


Just a cheeky repository with some base `Vagrantfiles` I use in a number of projects.
Each setup is based on an *almost* vanilla install of **Ubuntu 12.04 LTS x64 (Precise Pagolin)**
from [Vagrantbox.es][vagrantboxes].

##### `curl -O https://raw.github.com/adlawson/vagrantfiles/master/{LANG}/Vagrantfile`


 - [**Clojure**][vagrantfile-clojure] (Latest stable [Leiningen][leiningen] with OpenJDK 7)
 - [**Elixir**][vagrantfile-elixir] (Version 0.12.5 from github with [Rebar][rebar])
 - [**Erlang**][vagrantfile-erlang] (Latest stable from [`erlang-solutions.com`][erl-solutions] with [Rebar][rebar])
 - [**Go**][vagrantfile-go] (Version 1.2 via [Google Code][googlecode-go])
 - [**Haskell**][vagrantfile-haskell] (Haskell 2010 with latest stable GHC)
 - [**HHVM**][vagrantfile-hhvm] (Latest stable from [`ppa:mapnik/boost`][wiki-hhvm] with [Composer][composer])
 - [**Julia**][vagrantfile-julia] (Latest stable from [`ppa:staticfloat/juliareleases`][launchpad-julia])
 - [**Lua**][vagrantfile-lua] (Latest stable 5.2.x from Ubuntu repositories)
 - [**Node.js**][vagrantfile-nodejs] (Latest stable from [`ppa:chris-lea/node.js`][launchpad-nodejs])
 - [**Perl**][vagrantfile-perl] (Latest stable Perl 5 from Ubuntu repositories)
 - [**PHP**][vagrantfile-php] (Latest stable from [`ppa:ondrej/php5`][launchpad-php] with [Composer][composer])
 - [**Python**][vagrantfile-python] (Latest stable from apt repository)
 - [**Racket**][vagrantfile-racket] (Version 5.93)
 - [**Ruby**][vagrantfile-ruby] (Version 2.0.0 via `RVM`)
 - [**Scheme**][vagrantfile-scheme] (Latest stable mit-scheme from Ubuntu repositories)


[Vagrant][vagrant] will mount your directory to `/srv` via your provider's shared folder feature.
Alternatively, you can use NFS by replacing the `synced_folder` line with this:

```ruby
# Shared folders
config.vm.synced_folder ".", "/srv", :nfs => true

# Network
config.vm.network :private_network, ip: "33.33.33.101"
```


Other dependencies installed by default on every instance are:
 - cURL
 - Python Software Properties
 - Make
 - G++
 - Git
 - Cowsay *(important)*

### Performance
It may be important to you to limit the performance hit to your local machine, or ensure enough memory is available to your provider. For example, the configuration below will limit the VM to using no more than 50% of your CPU and allocate up to 2GB of memory. Note: This example uses VirtualBox, but if you use a different provider such as VMWare, then this will be ignored safely.

```
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    v.customize ["modifyvm", :id, "--memory", 2048]
  end
```

### Usage
Typically you won't want to download *all* configuration files, so rather than
cloning this project with git, a simple cURL download will do.
```bash
$ # Download the file for the language you want to use (nodejs in this example)
$ curl -O https://raw.github.com/adlawson/vagrantfiles/master/nodejs/Vagrantfile

$ # Create and SSH into the VM
$ vagrant up
$ vagrant ssh
...
Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic x86_64)

$ # Move into the mounted project directory
$ cd /srv
```


### License ###
The content of this library is released under the **MIT License** by **Andrew Lawson**.<br/>
You can find a copy of this license in [`LICENSE`][license] or at http://www.opensource.org/licenses/mit.


<!-- Links -->
[vagrant]: http://vagrantup.com
[vagrantboxes]: http://vagrantbox.es
[composer]: http://getcomposer.org
[erl-solutions]: https://www.erlang-solutions.com/downloads/download-erlang-otp
[googlecode-go]: https://code.google.com/p/go/downloads/list
[leiningen]: https://github.com/technomancy/leiningen
[launchpad-julia]: https://launchpad.net/~staticfloat/+archive/juliareleases
[launchpad-nodejs]: https://launchpad.net/~chris-lea/+archive/node.js
[launchpad-php]: https://launchpad.net/~ondrej/+archive/php5
[wiki-hhvm]: https://github.com/facebook/hhvm/wiki/Prebuilt-Packages-on-Ubuntu-12.04
[license]: /LICENSE
[rebar]: https://github.com/rebar/rebar
[vagrantfile-clojure]: /clojure/Vagrantfile
[vagrantfile-elixir]: /elixir/Vagrantfile
[vagrantfile-erlang]: /erlang/Vagrantfile
[vagrantfile-go]: /go/Vagrantfile
[vagrantfile-haskell]: /haskell/Vagrantfile
[vagrantfile-hhvm]: /hhvm/Vagrantfile
[vagrantfile-julia]: /julia/Vagrantfile
[vagrantfile-lua]: /lua/Vagrantfile
[vagrantfile-nodejs]: /nodejs/Vagrantfile
[vagrantfile-perl]: /perl/Vagrantfile
[vagrantfile-php]: /php/Vagrantfile
[vagrantfile-python]: /python/Vagrantfile
[vagrantfile-racket]: /racket/Vagrantfile
[vagrantfile-ruby]: /ruby/Vagrantfile
[vagrantfile-scheme]: /scheme/Vagrantfile
