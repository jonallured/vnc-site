desc 'Deploy site'
task :deploy do
  require 'dotenv'
  Dotenv.load

  system 'middleman build --clean'
  system "rsync -av -e ssh --delete build/ #{ENV['DEPLOY_TARGET']}"
end
