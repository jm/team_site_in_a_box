task :build do
  `nanoc`
end

task :deploy => [:build] do
  
end

task :serve do
  PageServer.serve!
end

task :setup do
  `git branch -m master source`
  `git push -u origin source`
  url = `git config --get remote.origin.url`.chomp
  `git clone #{url} output`
  `cd output && git symbolic-ref HEAD refs/heads/master && rm .git/index && git clean -fdx && touch index.html && git add . && git commit -a -m 'First markup' && git push origin master`
end