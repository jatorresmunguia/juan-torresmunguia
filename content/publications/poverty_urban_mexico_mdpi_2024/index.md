---
title: "Identifying Gender-Specific Risk Factors for Income Poverty across Poverty Levels in Urban Mexico: A Model-Based Boosting Approach"
subtitle: "published in Social Sciences" 
date: "2024-03-08"
date_end: "2024-03-08"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- journal-articles
- poverty
- 2024
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://www.mdpi.com/2076-0760/13/3/159/pdf?version=1710927898
- icon: link
  icon_pack: fas
  name: DOI
  url: https://doi.org/10.3390/socsci13030159
- icon: database
  icon_pack: fas
  name: Data
  url: https://doi.org/10.6084/m9.figshare.22132139.v1
- icon: code
  icon_pack: fas
  name: Code
  url: https://doi.org/10.6084/m9.figshare.22132139.v1
---
 
<h4> Abstract </h4>
This paper aims to identify income-poverty risk factors in urban Mexican households. Special emphasis is paid to examine differences between female- and male-headed families. To this, a dataset with 45 theoretical factors at the individual/household, community, and regional levels, integrating information from nine sources, is created. To these data, additive quantile models are estimated via the boosting algorithm. From a gender standpoint, the following main contributions come from this paper. First, educational lag is particularly relevant for female-headed households. Second, there is a gendered life cycle in the income trajectory for poor households with a head having a medium level of education. Third, some households, traditionally disregarded, are found to be even poorer: those lacking social connectedness, without credit cards, with an extended composition, in which the female head spends a large part of her time on housework, and families headed by young women with a medium level of education. Finally, communities and regions where families have a lower income-to-poverty ratio are characterized as having an unequal income distribution, lower human development, lower levels of women’s economic participation, poor quality of services, and lower gender-based violence levels in the public sphere but higher gender-based violence levels in the family context.

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
