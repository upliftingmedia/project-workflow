# Project Workflow

### Status
[![Build Status](https://semaphoreci.com/api/v1/upliftingmedia/project-workflow/branches/master/shields_badge.svg)](https://semaphoreci.com/upliftingmedia/project-workflow) | [![Code Climate](https://codeclimate.com/github/upliftingmedia/project-workflow/badges/gpa.svg)](https://codeclimate.com/github/upliftingmedia/project-workflow)

This is a website starter that can be used to create Ruby and Ruby on Rails applications using Vagrant.

This starter uses:

- Ruby [ 2.3.1 ]
- Rails [ 5.0.0 ]
- Vagrant

## How to use

1. Clone the repository

2. Run ```rm -rf .git/ && git init``` in order to reinitialise the project

3. Change the necessary folder, files and database names in the following files (There are comments the files listed below):
  * rename the folder ansible/roles/projectname to your app name
  * ansible/main.yml
  * ansible/roles/projectname/tasks/main.yml -- change the projectname folder to whatever your app is called
  * config/database.example.yml - this is an example database.yml file that you are free to use
  * config/initializers/session_store.rb

  There are comments in all of the above files.

4. If you wish to use VMware (this is generally faster that using virtualbox) then you will need to uncomment these lines of code:
  ```
  config.vm.provider "vmware_fusion" do |v|
    v.vmx["memsize"] = "1024"
    v.vmx["numvcpus"] = "1"
  end
  ```
  you will also need to install the vmware plugin and import the license for whatever version you are using i.e. VMware Fusion, VMware Workstation.
  Other then that keep the lines commented to use virtualbox.

5. If you are using MAC OS X or linux, be sure to create a ansible.cfg file
  * ~/.ansible.cfg (OS X)
  * /etc/ansible/.ansible.cfg (Ubuntu Linux)
  and add these lines of
  ```
  [defaults]
  allow_world_readable_tmpfiles=True
  deprecation_warnings=False
  ```

6. Run Vagrant up [This will create two virtual machines, web and db]

7. Have fun coding!

# Grid Options

## CSS Wizardry Grid
One option that is available is the CSS Wizardry Grid, comments are inside the ```_css_wizardry.scss``` file to show how to use the grid.

[https://github.com/csswizardry/csswizardry-grids](https://github.com/csswizardry/csswizardry-grids)

## Toast Grid
The second available option is the Toast Grid, this is an extremely simple to use, again comments are inside the ```_toast_grid.scss``` on how to use the grid.

#### NOTE: Both options are ready to use, just swap out the option that is not needed and delete the corresponding stylesheet and line from the ```application.scss```.



## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
