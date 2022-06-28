<h1 align="center">Data cleaning, exploration and visualization:</h1>
<h2 align="center">Federal Public Servers of Brazil</h2>


In this repository Im using data collected from the "Portal da Transparencia" API (https://api.portaldatransparencia.gov.br/) to conduct some data analysis.

# Introduction  

This is an independent project I did for learning purposes. I'm using python through jupyter notebooks to work with the data, performing filtering, cleaning, initial exploration and finally data visualization.

### Challenges
- Extracting the data
- Extracting insights and information from raw employee data
- Dealing with a of missing and invalid information
- Creating clean, understandable and informative visualization

# Tools and work

Data was loaded from a previously generated .csv with the data provided by the API `/api-de-dados/servidores` endpoint. I will add a repository with the scripts.  
Around 1 million rows were extracted with information about agency of assignment and agency of exercise, role, location and date of joining, among other data.
The libraries used were `pandas`,`matplotlib` and `seaborn` for most of the work, and `geopandas` and `geoplot` for the choropleth.

# Results

The data contained duplicates and missing values. Rows were filtered, cleaned and transformed to allow visualization.
Most of the military personel had little information, and was filtered out when I was analysing the date of joining and location.

- More than 36% of all the employees are the military, with roughtly 21% from de Army, 8.20% from Navy and 7.20% from Aeronautics.
![](/plots/divisão-servidores-exército.png)

- More than half of the servants assigned to the Ministery of Health are flagged as "on leave". Is the data correct? What does it mean?
- There is an agency called "Estados / Municipios / Empresas" (States, counties, companies) where all employees on exercise are flagged as "on leave"
- The agencies with the most employees assigned and on exercise are the Ministery of Health and Ministery of Economy, followed by EBSERH, INSS and UFRJ.
![](/plots/lotação-orgão-afastamento-civis.png)
![](/plots/exercicio-orgão-afastamento-civis.png)


- The most common role between civil servants is the University Professor, followed by other teachers and administrative agents.
  - There are also three roles with a lot of employees that involve infirmary.
 ![](/plots/servidores-civis-por-cargo.png)
 
- Hiring of civil servants had it's first increase during João Figueiredo's term, with the first peaks in 1985 and 1987, during José Sarney's term;
then id had a sharp fall with the bottom on Fernando Collor's term.
  - During Itamar Franco's term, hiring increased again, peaking by the end of his term and at the beginning of FHC's (Fernando Henrique Cardoso) term.
  - During FHC's term, hirind decreased once again and bottommed on his second term, only increasing again on his last year in the presidency.
  - During the first Lula's term, hiring remained high, but doubling at the end of his first term. The second term showed a increasing trend in hiring, peaking at his last year, 2010.
  - In Dilma's first term, hiring fell back from 2009 and 2010 numbers, but still maintaining a high average that was set by Lula. The number of public servants in Brazil peaked in 2015, with more than 40 thousand employees joining the federal service, on the election year, Dilma's final year of the first term.
  - After 2015, numbers fell again, forming a vale during Michel Temer's term and the start of Bolsonaro's term.
  - Bolsonaro's term shows increasing trend in hiring, suggesting it could once again have a higher than average number during the election year.
 
 ![](/plots/ingressantes-ano-mandato-eleição.png)
 
 - Finally, a distribution of the federal servants can be seen in the choropleth maps bellow.
 ![](/plots/total-servidores-estado.png)
 
 - And adjusted by the population of each state.
    - "Distrito Federal" was omitted from this map, as it has 4 times the second place number, and would make the heatmap useless.
 ![](/plots/servidores-100mil-estado.png)
 <table>
 <tr><th>Servidores por Estado</th><th>Servidores/100k habitantes</th></tr>
 <tr><td>
 
|Estado|Servidores|
|---|---|
|Distrito Federal|70056|
|Rio de Janeiro|62381|
|Minas Gerais|40197|
|Rio Grande do Sul|31991|
|São Paulo|27795|
|Bahia|15893|
|Paraná|15129|
|Pernambuco|14805|
|Pará|12442|
|Ceará|12330|
|Santa Catarina|12113|
|Paraíba|11789|
|Rio Grande do Norte|9774|
|Goiás|9712|
|Maranhão|7708|
|Espírito Santo|7270|
|Mato Grosso do Sul|6602|
|Amazonas|6358|
|Piauí|5746|
|Mato Grosso|5685|
|Alagoas|5531|
|Sergipe|4420|
|Roraima|4175|
|Tocantins|3277|
|Rondônia|3196|
|Amapá|2353|
|Acre|2344|
</td><td>

|Estado|Servidores/100k|
|---|---|
|Distrito Federal|2264|
|Roraima|640|
|Rio de Janeiro|357|
|Paraíba|290|
|Rio Grande do Sul|279|
|Rio Grande do Norte|274|
|Amapá|268|
|Acre|258|
|Mato Grosso do Sul|233|
|Tocantins|204|
|Sergipe|189|
|Minas Gerais|188|
|Espírito Santo|177|
|Rondônia|176|
|Piauí|175|
|Santa Catarina|165|
|Alagoas|164|
|Mato Grosso|159|
|Pernambuco|153|
|Amazonas|149|
|Pará|142|
|Goiás|135|
|Ceará|133|
|Paraná|130|
|Maranhão|108|
|Bahia|106|
|São Paulo|60|
</td></tr>
</table>
