
.PHONY: all clean data-for-app

all: clean types data-for-app

clean: clean-types

clean-types:
	rm -rf generated/**

types: clean-types
	cd .. && yarn install && yarn schema:totypes

tsv-data:
	python3 generate_data.py \
		--fetch

population:
	python3 generate_data.py \
		--output-population populationData.tsv

data-for-app:
	python3 generate_data.py \
		--output-scenarios ../src/assets/data/scenarios/scenarios.json \
		--output-cases ../src/assets/data/case_counts.json
