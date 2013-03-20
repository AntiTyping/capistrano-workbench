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
  task :default do
    backup
  end

  desc "Backups DB server"
  task :backup, :roles => :db do
    puts "Backing up DB server"
  end
end

namespace :asserts do
  desc "Checks free space"
  task :free_space, :roles => :db do
    puts "Checking free space"
  end
end

namespace :notifier do
  desc "E-mails admin"
  task :email_admin, :roles => :db do
    puts "E-mailing admin"
  end
end

namespace :logs do
  desc "Follows production log"
  task :watch do
    stream("tail -f /u/apps/example.com/log/production.log")
  end
end

before "db:backup", "asserts:free_space"
after "db:backup", "notifier:email_admin"
