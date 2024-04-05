---
title: "A global dataset of pandemic- and epidemic-prone disease outbreaks"
subtitle: "published in Springer Nature's Scientific Data" 
date: "2022-11-10"
date_end: "2022-11-10"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA, Florina Cristina Badarau, Luis Rodrigo Díaz Pavez, Inmaculada Martínez-Zarzoso & Konstantin M. Wacker"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- journal-articles
- datasets
- outbreaks
- 2022
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://www.nature.com/articles/s41597-022-01797-2.pdf
- icon: link
  icon_pack: fas
  name: DOI
  url: https://doi.org/10.1038/s41597-022-01797-2
- icon: database
  icon_pack: fas
  name: Data
  url: https://doi.org/10.6084/m9.figshare.17207183.v2
- icon: code
  icon_pack: fas
  name: Code
  url: https://doi.org/10.6084/m9.figshare.17207183.v2
- icon: github
  icon_pack: fab
  name: GitHub
  url:  https://github.com/jatorresmunguia/DiseaseOutbreaksData
- icon: r-project
  icon_pack: fab
  name: ShinyApp
  url: https://jatorresmunguia.shinyapps.io/A_global_dataset_of_disease_outbreaks/
---
 
<h4> Abstract </h4>
This paper presents a new dataset of infectious disease outbreaks collected from the Disease Outbreak News and the Coronavirus Dashboard produced by the World Health Organization. The dataset contains information on 70 infectious diseases and 2227 public health events that occurred over the period from January 1996 to March 2022 in 233 countries and territories around the world. We illustrate the potential use of this dataset to the research community by analysing the spatial distribution of disease outbreaks. We find evidence of spatial clusters of high incidences (“hot spots”) in Africa, America, and Asia. This spatial analysis enables policymakers to identify the regions with the greatest likelihood of suffering from disease outbreaks and, taking into account their degree of preparedness and vulnerability, to develop policies that may help contain the spreading of future outbreaks. Further applications could focus on combining our data with other information sources to study, for instance, the link between environmental, globalization, and/or socioeconomic factors with disease outbreaks.

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
