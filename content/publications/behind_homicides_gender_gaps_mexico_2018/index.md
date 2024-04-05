---
title: "What is behind homicide gender gaps in Mexico? A spatial semiparametric approach"
subtitle: "published in Ibero-America Institute for Economic Research (IAI) discussion papers"
date: "2018-01-01"
date_end: "2018-01-01"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA & Inmaculada Martínez-Zarzoso"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- working-papers
- violence
- 2018
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://www.econstor.eu/bitstream/10419/178674/1/1023106922.pdf
- icon: link
  icon_pack: fas
  name: DOI
  url: http://hdl.handle.net/10419/178674
---

<h4> Abstract </h4>
From 1990 to 2016, more than 425,000 homicides have occurred in Mexico. In 2016, the country recorded the world´s second largest number of conflict fatalities with more than 24,000 killings. Despite the growing attention for inquiring into specific causes of homicide victimization, research on the matter suffer from three important shortcomings: disregard for introducing a gender perspective, lack of a multilevel approach -use of information both at the victim and community levels- and the exclusive use of traditional linear models -failing to capture nonlinear relationships, as can be expected, in the linkage between age of a person and their likelihood of being victim of crime-. In order to contribute to the analysis of homicides in Mexico, the present study develops a semiparametric approach to investigate the determinants of gender bias in homicide victimization in Mexico. Homicide statistics from 2010 to 2014 and 2010 census data are used to construct a logistic model with sex of the victim as response variable and a set of potential categorical and continuous covariates. The main results suggest that gender differences in victimization can be explained by the mechanism of killing, interaction between age of the victim and the killing mechanism, social deprivation of the municipality of occurrence, share of the population living in female-headed households, share of the population living in indigenous-headed households, random effects and spatial effects.

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