require 'grit'

task :vim do
   dir = 'intro-vim'
   repo = 'git://github.com/icco/intro-to-vim-talk.git'

   # delete old crap
   Kernel.system("rm -rf #{dir}")

   # clone git://github.com/icco/intro-to-vim-talk.git
   Kernel.system("git clone #{repo}")

   # showoff static
   # rename dir
   # commit
end
 
task :default => [ :vim ] do
   # ...
end
