#!/usr/bin/env ruby

require 'fileutils'

task :vim do
   dir = 'vim'
   repo = 'git://github.com/icco/intro-to-vim-talk.git'
   repoDir = 'intro-to-vim-talk'

   # delete old crap
   Kernel.system("rm -rf #{dir} #{repoDir}")

   # clone git://github.com/icco/intro-to-vim-talk.git
   Kernel.system("git clone #{repo}")

   # showoff static
   chdir(repoDir)
   Kernel.system("showoff static")

   # rename dir
   FileUtils.mv('static', "../#{dir}")
   chdir('..')

   # commit
   msg = 'Updating vim talk'
   Kernel.system("git add #{dir}")
   Kernel.system("git ci -m \"#{msg}\"")
   Kernel.system("rm -rf #{repoDir}")
end
 
task :default => [ :vim ] do
   # ...
end
