require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'
require 'rcov/rcovtask'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |s|
    s.name = "ruby_protobuf"
    s.executables = %w(mk_parser rprotoc ruby_protobuf)
    s.summary = "Protocol Buffers for Ruby"
    s.homepage = "http://github.com/chrisk/ruby_protobuf"
    s.files =  FileList["[A-Z]*", "{bin,examples,lib,test}/**/*"]
  end
rescue LoadError
  puts "Jeweler, or one of its dependencies, is not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

Rake::TestTask.new do |t|
  t.libs << 'lib' << 'test'
  t.pattern = 'test/**/test_*.rb'
end

task :default => :test

Rcov::RcovTask.new do |t|
  t.libs << "lib" << "test"
  t.test_files = FileList['test/test_*.rb']
  t.verbose = true
end

Rake::RDocTask.new do |rdoc|
  rdoc.rdoc_dir = 'doc'
  rdoc.title = 'ruby_protobuf Documentation'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('LICENSE*')
  rdoc.rdoc_files.include('History.txt')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
