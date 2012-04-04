
task :check_versions do
  puts "## Check program versions"
  ["firefox", "mysql", "psql", "ruby", "gem", "bundle", "Xvfb"].each do |bin|
    version = `#{bin} --version 2>/dev/null || apt-show-versions #{bin.downcase} 2>/dev/null || echo "not found :("`.sub(/\n(.+)/, ", \1")
    path = `which #{bin} 2>/dev/null || echo "not found :("`

    puts "  # Testing #{bin}"
    puts "  -- version: #{version}"
    puts "  -- path:    #{path}"
    puts ""
  end
end

task :list_processes do
  puts "## Listing processes"
  puts `ps ux`
end

task :travis => [:check_versions, :list_processes] do
  puts "## Done"
end
