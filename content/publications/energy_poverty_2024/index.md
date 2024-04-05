---
title: "Mapping energy poverty measures during the COVID-19 pandemic: A new global panel dataset"
subtitle: "published in International Network for Economic Research working papers" 
date: "2024-04-03"
date_end: "2024-04-03"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA, Marlies Hesselman, Inmaculada Martínez-Zarzoso & Ilse Ruyssen"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- working-papers
- poverty
- datasets
- 2024
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://infer-research.eu/wp-content/uploads/2024/04/WP2024.04.pdf
- icon: database
  icon_pack: fas
  name: Data
  url:  https://doi.org/10.6084/m9.figshare.22652320
- icon: code
  icon_pack: fas
  name: Code
  url:  https://doi.org/10.6084/m9.figshare.22652320
- icon: github
  icon_pack: fab
  name: GitHub
  url:  https://github.com/jatorresmunguia/EnergyPoverty
- icon: r-project
  icon_pack: fab
  name: ShinyApp
  url: https://jatorresmunguia.shinyapps.io/DashboardEnergyPov/?_ga=2.12193140.1599365608.1647015703-2050109591.1646912998
---
 
<h4> Abstract </h4>
This paper compiles and presents a global panel dataset of energy poverty policy actions spanning the period March 2020 and March 2021. It builds on the COVID-19 Energy Map that collects policies to ensure the affordability of energy supplies for households during the COVID-19 pandemic. The monthly-frequency dataset is organized in a user-friendly way, allowing not only experts and researchers, but also the broader non-expert public, to examine and analyse the month-by-month policy changes across countries. The panel dataset is widely applicable for future research, especially as other global or regional datasets pertaining to the early years of the pandemic become available.

<h4 id="citation">Citation</h4>
<div id="citation-content"></div>

<script>
function generateCitationHTML(entry) {
  const authors = `<strong>${entry.author.replace(/[{}]/g, '').replace(/,(\s*)$/, '')}</strong>`;
  const year = entry.year.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const title = entry.title.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const volume = entry.volume.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const number = entry.number.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const journal = entry.journal.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const url = entry.url.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const doi = entry.doi.replace(/[{}]/g, '').replace(/,(\s*)$/, '');

  const citationHTML = `
    <p>${authors} (${year}) <em>${title}</em>. ${journal}, ${volume}(${number}). <a href="${url}" target="_blank">${doi}</a>.</p>
    <p>Download the article citation in BibTex format (compatible with BibDesk, LaTeX) <a href="cite.bib"><i class="fas fa-file-download"></i></a>.</p>
  `;
  
  return citationHTML;

}

  // Main function to fetch .bib file and generate HTML
  function main() {
    // AJAX request to fetch .bib file
    var xhr = new XMLHttpRequest();
    xhr.open("GET", "cite.bib", true);
    xhr.onreadystatechange = function() {
      if (xhr.readyState == 4 && xhr.status == 200) {
        // Parse BibTeX into JSON
        var bibData = parseBibtex(xhr.responseText);

        // Generate HTML for each entry
        var citationDiv = document.getElementById('citation-content');
        bibData.entries.forEach(entry => {
          const citationHTML = generateCitationHTML(entry);
          citationDiv.innerHTML += citationHTML;
        });
      }
    };
    xhr.send();
  }

  // Parse BibTeX into JSON
  function parseBibtex(bibtex) {
    // Split BibTeX into individual entries
    var entries = bibtex.split('\n\n');

    // Initialize an array to store parsed entries
    var parsedEntries = [];

    // Parse each entry
    entries.forEach(entry => {
      // Split entry into lines
      var lines = entry.split('\n');

      // Initialize an object to store parsed entry fields
      var parsedEntry = {};

      // Parse each field
      lines.forEach(line => {
        // Ignore empty lines and comments
        if (line.trim() !== '' && !line.startsWith('%')) {
          // Split line into key and value
          var parts = line.split('=');
          var key = parts[0].trim();
          var value = parts.slice(1).join('=').trim();

          // Store key-value pair in parsed entry
          parsedEntry[key] = value;
        }
      });

      // Add parsed entry to array
      parsedEntries.push(parsedEntry);
    });

    // Return parsed entries
    return { entries: parsedEntries };
  }

  // Run main function
  main();
</script>
