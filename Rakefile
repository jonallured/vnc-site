# frozen_string_literal: true

require 'rubocop/rake_task'
RuboCop::RakeTask.new(:rubocop)

desc 'Build Middleman site'
task :build do
  exit 1 unless system './bin/build'
end

desc 'Deploy site'
task deploy: :build do
  require 'dotenv'
  Dotenv.load
  exit 2 unless system "DEPLOY_TARGET=#{ENV['DEPLOY_TARGET']} ./bin/deploy"
end

task default: %i[rubocop build]
