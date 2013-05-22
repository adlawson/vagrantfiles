# Vagrantfiles #


Just a cheeky repository with some base `Vagrantfiles` I use in a number of projects.
Each setup is based on an *almost* vanilla install of **Ubuntu 12.04 LTS x64 (Precise Pagolin)**
from [Vagrantbox.es][vagrantboxes] and simply uses `apt-get` to install dependencies.


 - [**Node.js**][vagrantfile-nodejs] (Latest stable from ppa:chris-lea/node.js)
 - [**PHP**][vagrantfile-php] (Latest stable from ppa:ondrej/php5 *plus* [Composer][composer])
 - [**Python**][vagrantfile-python] (Latest stable from apt repository)
 - [**Ruby**][vagrantfile-ruby] (Version 2.0.0 via RVM)


Vagrant will mount your directory to `/srv` via your privider's shared folder feature.
Alternatively, you can use NFS by replacing the `synced_folder` line with this:

```ruby
# Shared folders
config.vm.synced_folder '.', '/srv', :nfs => true

# Network
config.vm.network :private_network, ip: '33.33.33.101'
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
You can find a copy of this license at http://www.opensource.org/licenses/mit or in [`LICENSE`][license]


<!-- Links -->
[vagrant]:            http://vagrantup.com
[vagrantboxes]:       http://vagrantbox.es
[license]:            https://github.com/adlawson/vagrantfiles/blob/master/LICENSE
[composer]:           http://getcomposer.org
[vagrantfile-nodejs]: https://github.com/adlawson/vagrantfiles/blob/master/nodejs/Vagrantfile
[vagrantfile-php]:    https://github.com/adlawson/vagrantfiles/blob/master/php/Vagrantfile
[vagrantfile-python]: https://github.com/adlawson/vagrantfiles/blob/master/python/Vagrantfile
[vagrantfile-ruby]:   https://github.com/adlawson/vagrantfiles/blob/master/ruby/Vagrantfile
[launchpad-nodejs]:   https://launchpad.net/~chris-lea/+archive/node.js
[launchpad-php]:      https://launchpad.net/~ondrej/+archive/php5
