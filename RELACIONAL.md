TRANSFORMACIÓN AL MODELO RELACIONAL

ENTIDADES PRINCIPALES
Country(code, name, capital, province, area, population)
Province(name, country_code, population, area, capital, capprov)
City(name, country_code, province_name, population, latitude, longitude, elevation)
Continent(name, area)
Economy(country_code, gdp, agriculture, service, industry, inflation, unemployment)
Population(country_code, population_growth, infant_mortality)
Politics(country_code, independence, wasdependent, dependent, government)
Religion(country_code, name, percentage)
EthnicGroup(country_code, name, percentage)
Language(country_code, name, percentage)
Sublanguage(sublang, suplang)
CountryPops(country_code, year, population)
ProvincePops(province_name, country_code, year, population)
CityPops(city_name, country_code, province_name, year, population)
CountryOtherName(country_code, othername)
CountryLocalName(country_code, localname)
ProvinceOtherName(province_name, country_code, othername)
ProvinceLocalName(province_name, country_code, localname)
CityOtherName(city_name, country_code, province_name, othername)
CityLocalName(city_name, country_code, province_name, localname)
Airport(iatacode, name, country_code, city_name, province_name, island_name,
latitude, longitude, elevation, gmtoffset)

Organization(abbreviation, name, city_name, country_code, province_name,
established)

ENTIDADES GEOGRÁFICAS
Mountain(name, mountains, elevation, type, coordinates)
Desert(name, area, coordinates)
Island(name, islands, area, elevation, type, coordinates)
Lake(name, river, area, elevation, depth, height, type, coordinates)
Sea(name, area, depth)
River(name, river, lake, sea, length, area, source, mountains, sourceelevation,
estuary, estuaryelevation)

RELACIONES (transformadas en tablas)
Encompasses(country_code, continent_name, percentage)
Borders(country_code1, country_code2, length)
IsMember(country_code, organization_abbreviation, type)

RELACIONES GEOGRÁFICAS (ubicaciones)
Geo_Mountain(mountain_name, country_code, province_name)
Geo_Desert(desert_name, country_code, province_name)
Geo_Island(island_name, country_code, province_name)
Geo_River(river_name, country_code, province_name)
Geo_Sea(sea_name, country_code, province_name)
Geo_Lake(lake_name, country_code, province_name)

Geo_Source(river_name, country_code, province_name)
Geo_Estuary(river_name, country_code, province_name)

RELACIONES DE FLUJOS
RiverThrough(river_name, lake_name)
MergesWith(sea1_name, sea2_name)
Located(city_name, province_name, country_code, river_name, lake_name,
sea_name)
LocatedOn(city_name, province_name, country_code, island_name)
IslandIn(island_name, sea_name, lake_name, river_name)
MountainOnIsland(mountain_name, island_name)
LakeOnIsland(lake_name, island_name)
RiverOnIsland(river_name, island_name)
