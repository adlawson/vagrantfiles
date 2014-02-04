# Vagrantfiles #


Just a cheeky repository with some base `Vagrantfiles` I use in a number of projects.
Each setup is based on an *almost* vanilla install of **Ubuntu 12.04 LTS x64 (Precise Pagolin)**
from [Vagrantbox.es][vagrantboxes] and simply uses `apt-get` to install dependencies.


 - [**Elixir**][vagrantfile-elixir] (Version 0.12.2 from github)
 - [**Erlang**][vagrantfile-erlang] (Latest stable from [`erlang-solutions.com`][erl-solutions])
 - [**Go**][vagrantfile-go] (Version 1.2 via [Google Code][googlecode-go])
 - [**Haskell**][vagrantfile-haskell] (Haskell 2010 with latest stable GHC)
 - [**Julia**][vagrantfile-julia] (Latest stable from [`ppa:staticfloat/juliareleases`][launchpad-julia])
 - [**Node.js**][vagrantfile-nodejs] (Latest stable from [`ppa:chris-lea/node.js`][launchpad-nodejs])
 - [**PHP**][vagrantfile-php] (Latest stable from [`ppa:ondrej/php5`][launchpad-php] *plus* [Composer][composer])
 - [**Python**][vagrantfile-python] (Latest stable from apt repository)
 - [**Ruby**][vagrantfile-ruby] (Version 2.0.0 via `RVM`)


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


### License ###
The content of this library is released under the **MIT License** by **Andrew Lawson**.<br/>
You can find a copy of this license in [`LICENSE`][license] or at http://www.opensource.org/licenses/mit.


<!-- Links -->
[vagrant]: http://vagrantup.com
[vagrantboxes]: http://vagrantbox.es
[composer]: http://getcomposer.org
[erl-solutions]: https://www.erlang-solutions.com/downloads/download-erlang-otp
[googlecode-go]: https://code.google.com/p/go/downloads/list
[launchpad-julia]: https://launchpad.net/~staticfloat/+archive/juliareleases
[launchpad-nodejs]: https://launchpad.net/~chris-lea/+archive/node.js
[launchpad-php]: https://launchpad.net/~ondrej/+archive/php5
[license]: /LICENSE
[vagrantfile-elixir]: /elixir/Vagrantfile
[vagrantfile-erlang]: /erlang/Vagrantfile
[vagrantfile-go]: /go/Vagrantfile
[vagrantfile-haskell]: /haskell/Vagrantfile
[vagrantfile-julia]: /julia/Vagrantfile
[vagrantfile-nodejs]: /nodejs/Vagrantfile
[vagrantfile-php]: /php/Vagrantfile
[vagrantfile-python]: /python/Vagrantfile
[vagrantfile-ruby]: /ruby/Vagrantfile
