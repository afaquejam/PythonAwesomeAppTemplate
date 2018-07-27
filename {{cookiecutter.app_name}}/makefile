all:
	./{{cookiecutter.app_name}}

test:
	python -m pytest

test_report:
	mkdir -p reports
	python3 -m pytest --cov-config .coveragerc --cov-report html:reports/{{cookiecutter.package_name}} --cov={{cookiecutter.package_name}}
	-firefox reports/{{cookiecutter.package_name}}/index.html &

upgrade-dependencies:
	pip freeze — local | grep -v ‘^\-e’ | cut -d = -f 1 | xargs -n1 pip install -U

clean:
	-find . -name "*.log" -delete
	-find . -name "*.pyc" -delete
	-find . -name "__pycache__" -delete
	-rm -rf .pytest_cache
	-rm -rf reports
	-rm -rf {{cookiecutter.app_name}}.spec build dist

hard-clean:
	-rm -rf virtualenv
