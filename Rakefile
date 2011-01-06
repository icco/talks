#!/usr/bin/env ruby

require 'fileutils'

def build_showoff dir, repo, repoDir
   # delete old crap
   Kernel.system("rm -rf #{dir} #{repoDir}")

   # clone git://github.com/icco/intro-to-vim-talk.git
   Kernel.system("git clone #{repo}")

   # showoff static
   chdir(repoDir)
   Kernel.system("/home/nat/Projects/showoff/bin/showoff static")

   # rename dir
   FileUtils.mv('static', "../#{dir}")
   chdir('..')

   # commit
   msg = "Updating #{dir} talk"
   Kernel.system("git add #{dir}")
   Kernel.system("git ci -m \"#{msg}\"")
   Kernel.system("rm -rf #{repoDir}")
end

task :vim do
   dir = 'vim'
   repo = 'git://github.com/icco/intro-to-vim-talk.git'
   repoDir = 'intro-to-vim-talk'

   build_showoff dir, repo, repoDir
end

task :presence do
   dir = 'presence'
   repo = 'git@github.com:icco/web-presence-talk.git'
   repoDir = 'web-presence-talk'

   build_showoff dir, repo, repoDir
end
 
task :default => [ :vim, :presence ] do
   # ...
end
