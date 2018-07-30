all:
	./{{cookiecutter.app_name}}

test:
	python -m pytest

test_report:
	mkdir -p reports
	python3 -m pytest --cov-config .coveragerc --cov-report html:reports/{{cookiecutter.package_name}} --cov={{cookiecutter.package_name}}
	-firefox reports/{{cookiecutter.package_name}}/index.html &

freeze-dependencies:
	pip3 freeze > requirements.txt

upgrade-dependencies:
	pip3 install -r requirements-to-freeze.txt --upgrade

clean:
	-find . -name "*.log" -delete
	-find . -name "*.pyc" -delete
	-find . -name "__pycache__" -delete
	-rm -rf .pytest_cache
	-rm -rf reports
	-rm -rf {{cookiecutter.app_name}}.spec build dist

hard-clean: clean
	-rm -rf virtualenv
