desc 'Build Middleman site'
task :build do
  exit 1 unless system 'bundle exec middleman build --clean'
end

desc 'Deploy site'
task deploy: :build do
  require 'dotenv'
  Dotenv.load
  exit 2 unless system "rsync -av -e ssh --delete build/ #{ENV['DEPLOY_TARGET']}"
end

task default: [:build]
