task :ls_home, :hosts => 'batman' do
  run 'ls'
end

namespace :web do
  desc "Backups WEB server"
  task :backup, :roles => :web  do
    puts "Backing up WEB server"
  end
end

namespace :db do
  desc "Backups DB server"
  task :bakup, :roles => :db do
    puts "Backing up DB server"
  end
end
