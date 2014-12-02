# Vagrantfiles

Just a cheeky repository with some base `Vagrantfiles` I use in a number of
projects. Each setup is based on a vanilla installation of
[Ubuntu 14.04 LTS (Trusty Tahr)][ubuntu] from [Vagrant Cloud][boxes].

## How do I use it?
To download a vagrant box for your project, just run the following. Remember to
replace `$LANG` with an available language from the list below.
```bash
curl -O https://raw.githubusercontent.com/adlawson/vagrantfiles/master/$LANG/Vagrantfile
vagrant up
vagrant ssh
cd /srv
```

## Available languages
| Language               | Tooling                  | Version                                                     | Extras        |
| ---------------------- | ------------------------ | ----------------------------------------------------------- | ------------- |
| [clojure][raw-clojure] | [`Leiningen`][leiningen] | `stable`                                                    | `default-jre` |
| [elixir][raw-elixir]   | [`Mix`][mix]             | `latest` from [`erlang-solutions.com`][src-erlang]          |               |
| [erlang][raw-erlang]   | [`Rebar`][rebar]         | `latest` from [`erlang-solutions.com`][src-erlang]          |               |
| [golang][raw-golang]   | [`Godep`][godep]         | `1.3.3` from [`golang.org`][src-golang]                     |               |
| [haskell][raw-haskell] |                          | `2010`                                                      |               |
| [hhvm][raw-hhvm]       | [`Composer`][composer]   | `latest` from [`ppa:mapnik/boost`][ppa-hhvm]                |               |
| [julia][raw-julia]     |                          | `latest` from [`ppa:staticfloat/juliareleases`][ppa-julia]  |               |
| [lua][raw-lua]         |                          | `5.2.*`                                                     |               |
| [nodejs][raw-nodejs]   | [`NPM`][npm]             | `latest` from [`ppa:chris-lea/node.js`][ppa-nodejs]         |               |
| [perl][raw-perl]       |                          | `5.*`                                                       |               |
| [php][raw-php]         | [`Composer`][composer]   | `5.6.*` from [`ppa:ondrej/php5-5.6`][ppa-php]               |               |
| [python][raw-python]   | [`Pip`][pip]             | `3.4.*` and `2.7.*` (`python3` and `python`)                |               |
| [racket][raw-racket]   |                          | `5.93`                                                      |               |
| [ruby][raw-ruby]       | [`Gem`][gem]             | `2.0.0`                                                     | [`RVM`][rvm]  |
| [rust][raw-rust]       | [`Cargo`][cargo]         | `stable`                                                    |               |
| [scala][raw-scala]     | [`SBT`][sbt]             | `2.11.2`                                                    | `default-jre` |
| [scheme][raw-scheme]   |                          | `latest mit-scheme`                                         |               |

## Configuration

### Static IP
To add support for a static IP address to your box, add the following to the
Vagrantfile after download:
```ruby
# Network
config.vm.network :private_network, ip: "10.10.10.100"
```

### NFS
If you prefer NFS to the default network filesystem provided by your VM, replace
the `# Shared folders` lines in the Vagrantfile with the following. You will
need a Static IP for this to work correctly.
```ruby
# Shared folders
config.vm.synced_folder ".", "/srv", :nfs => true
```

## License
The content of this library is released under the **MIT License** by
**Andrew Lawson**.<br/> You can find a copy of this license in
[`LICENSE`][license] or at http://opensource.org/licenses/mit.

[boxes]:       https://vagrantcloud.com
[license]:     LICENSE
[ubuntu]:      http://www.ubuntu.com/server
[vagrant]:     https://vagrantup.com

[ppa-hhvm]:    https://github.com/facebook/hhvm/wiki/Prebuilt-Packages-on-Ubuntu-12.04
[ppa-julia]:   https://launchpad.net/~staticfloat/+archive/juliareleases
[ppa-nodejs]:  https://launchpad.net/~chris-lea/+archive/node.js
[ppa-php]:     https://launchpad.net/~ondrej/+archive/php5-5.6
[src-erlang]:  https://www.erlang-solutions.com/downloads/download-erlang-otp
[src-golang]:  https://golang.org/dl/

[cargo]:       http://crates.io
[composer]:    https://getcomposer.org
[gem]:         https://rubygems.org
[godep]:       https://github.com/tools/godep
[leiningen]:   https://github.com/technomancy/leiningen
[mix]:         http://elixir-lang.org/getting_started/mix_otp/1.html
[npm]:         https://www.npmjs.org
[pip]:         http://pip.readthedocs.org/en/latest
[rebar]:       https://github.com/rebar/rebar
[rvm]:         https://rvm.io
[sbt]:         http://www.scala-sbt.org

[raw-clojure]: https://raw.githubusercontent.com/adlawson/vagrantfiles/master/clojure/Vagrantfile
[raw-elixir]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/elixir/Vagrantfile
[raw-erlang]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/erlang/Vagrantfile
[raw-golang]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/golang/Vagrantfile
[raw-haskell]: https://raw.githubusercontent.com/adlawson/vagrantfiles/master/haskell/Vagrantfile
[raw-hhvm]:    https://raw.githubusercontent.com/adlawson/vagrantfiles/master/hhvm/Vagrantfile
[raw-julia]:   https://raw.githubusercontent.com/adlawson/vagrantfiles/master/julia/Vagrantfile
[raw-lua]:     https://raw.githubusercontent.com/adlawson/vagrantfiles/master/lua/Vagrantfile
[raw-nodejs]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/nodejs/Vagrantfile
[raw-perl]:    https://raw.githubusercontent.com/adlawson/vagrantfiles/master/perl/Vagrantfile
[raw-php]:     https://raw.githubusercontent.com/adlawson/vagrantfiles/master/php/Vagrantfile
[raw-python]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/python/Vagrantfile
[raw-racket]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/racket/Vagrantfile
[raw-ruby]:    https://raw.githubusercontent.com/adlawson/vagrantfiles/master/ruby/Vagrantfile
[raw-rust]:    https://raw.githubusercontent.com/adlawson/vagrantfiles/master/rust/Vagrantfile
[raw-scala]:   https://raw.githubusercontent.com/adlawson/vagrantfiles/master/scala/Vagrantfile
[raw-scheme]:  https://raw.githubusercontent.com/adlawson/vagrantfiles/master/scheme/Vagrantfile
