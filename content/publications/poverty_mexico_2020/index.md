---
title: "What Determines Poverty in Mexico?: A Quantile Regression Approach"
subtitle: "published in Ibero-America Institute for Economic Research (IAI) discussion papers"
date: "2020-01-01"
date_end: "2020-01-01"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA & Inmaculada Martínez-Zarzoso"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- working-papers
- poverty
- 2020
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://www.econstor.eu/bitstream/10419/217231/1/1698314159.pdf
- icon: link
  icon_pack: fas
  name: DOI
  url: http://hdl.handle.net/10419/217231
---

<h4> Abstract </h4>
According to official poverty estimates in Mexico, more than 50 percent of the population was poor in 2016, half of which could not even afford the basic food basket. Whereas most of the existing research analyses poverty focusing exclusively on average income or on the expected probability of being poor, this paper departs from this approach by analyzing income differences between households in rural and urban settlements using boosting additive quantile models. The models are estimated using a cross-sectional dataset containing information of more that 50 thousand households for the year 2015. The main results highlight the importance of analyzing poverty from an individual, household, community and regional perspectives and the relevance of accounting for heterogeneity of the effects on female- and male-headed households. The results point towards the existence of a life-income cycle and the relevance of education, social networks, income equality and quality of government to fight poverty. The findings also indicate that economic empowerment of women matters for pro-poor income policies to be effective and point towards the need of introducing a gender approach in the study on poverty.

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