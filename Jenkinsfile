node {
    stage 'Preparing VirtualEnv'
    if (!fileExists('.env')){
        echo 'Creating virtualenv ...'
        sh 'virtualenv --no-site-packages .env'
    }
    sh '. .env/bin/activate'
    sh 'ls -all'
   sh """
. .env/bin/activate
if [[ -f requirements/preinstall.txt ]]; then
    pip install -r requirements/preinstall.txt
fi
pip install -r requirements/test.txt
./manage.py test --noinput
"""
}
