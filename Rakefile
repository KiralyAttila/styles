
require 'bundler'
begin
  Bundler.setup
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install' to install missing gems"
  exit e.status_code
end

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  if ENV['TRAVIS']
    spec.rspec_opts = %w{ --require spec_helper.rb --format Fuubar --color }
  else
    spec.rspec_opts = %w{ --require spec_helper.rb --format progress --color }
  end
end

task :default => [:spec]
