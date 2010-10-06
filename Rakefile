require 'grit'

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
   mv 'static' "../#{dir}"

   # commit
   msg = 'Updating vim talk'
   Kernel.system("git ci -a -m \"#{msg}\"")
end
 
task :default => [ :vim ] do
   # ...
end
