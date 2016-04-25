# Guardfile

require 'asciidoctor'
require 'erb'

guard 'shell' do
watch(/^*\.adoc$/) {|m|
  Asciidoctor.render_file('presentation.adoc', :to_file => 'presentation/index.html', :template_dir => 'asciidoctor-reveal.js/templates/slim/')
}
end

# guard 'livereload' do
#   watch(%r{^.+\.(css|js|html)$})
# end
