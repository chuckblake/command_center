
# Controller Actions

def index
  @sections = [
    {
      name: "✅ Reviews",
      description: "System-level and domain-specific audits.",
      reports: [
        {
          name: "System Review Page",
          description: "Code quality, architecture, performance, infrastructure health.",
          link: command_center_report_path(report_directory: "system_review")
        }
      ]
    }
  ]
end

def show_report
  report_directory = params[:report_directory]
  display_report_content(report_directory)
end

# Generic method to handle report display (for system_review, security_review, integrations)
def display_report_content(report_directory)
  files = load_report_files(report_directory)
  @example_files = files.map { |f| f[:name] }
  selected = params[:report_name].presence || @example_files.last

  if selected && files.any?
    file_entry = files.find { |f| f[:name] == selected }
    load_markdown_file(file_entry)
  else
    @markdown = "# No #{report_directory.humanize} Markdown files found."
    @selected_file = nil
    @error = nil
  end
end
