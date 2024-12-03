for windows
install requirements using the command `pip install -r requirements.txt`

run Redis server on port 6379
for celery task run this command on seprate termnial `celery -A taskdemo worker -l info `

for celery cron job task run this command on separate termnial `celery -A taskdemo beat -l info `

run django server using command `python manage.py runserver` // it will by default run on 8000 port (http://127.0.0.1:8000)

to check ceelry task hit this endpoint - GET http://127.0.0.1:8000/demo/

to create cron job hit this endpoint - POST http://127.0.0.1:8000/task/

payload: {    
    "name": "helloworld",
    "task": "app.tasks.print_hello",
    "args": "[]",
    "kwargs": "{}",
    "queue": null,
    "exchange": null,
    "routing_key": null,
    "headers": "{}",
    "priority": null,
    "expires": null,
    "expire_seconds": null,
    "one_off": false,
    "start_time": null,
    "enabled": false,
    "last_run_at": null,
    "total_run_count": 0,
    "date_changed": "2024-12-03T14:09:40.488046Z",
    "description": "",
    "interval": 1,
    "crontab": null,
    "solar": null,
    "clocked": null
}

to update(disable) cron job hit this endpoint - PATCH http://127.0.0.1:8000/task/<task-id>/

payload: {
  "enabled": false
}

to delete cron job hit this endpoint - DELETE http://127.0.0.1:8000/task/
