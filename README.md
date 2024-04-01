# vet
https://vite.koloboks.de/welcome?id=5
?id - чтобы убедиться что nginx передает корректно параметры


vite 
	современный и быстрый инструмент сборки: javaScript, TypeScript,  ES модули (ESM).  
	использует прямое выполнение кода в браузере с помощью ESM (ECMAScript модули) без предварительной сборки. 
	c vite изменения применяются мгновенно благодаря прямому выполнению кода в браузере, в отличие 
	от CRA которому требуется время на пересборку проекта (webpack и React Hot Loader) при каждом изменении кода.
	Vite поддерживает React и может использоваться для разработки React-приложений так же, как и Webpack.


Деплой Frontend приложения. Настройка nginx. Подключаем домен, настраиваем HTTPS, gzip, docker
https://www.youtube.com/watch?v=8OHe6chCWTE

# install
https://github.com/utimur/vite-boilerplate/
git@github.com:utimur/vite-boilerplate.git

"scripts": {
    "dev": "vite",
    "build": "tsc && vite build"
  },

local development
>npm run dev

strato home/webmaster
git@github.com:utimur/vite-boilerplate.git

host:
	>sudo apt update
	git		>sudo apt install git-all
	>git clone in >cd ~
	nvm 		....node version manager https://github.com/nvm-sh/nvm
	>nvm install <node version>		
	>node -v
	>nmp -v

	>npm run build	
	>sudo apt install nginx

# subdomains
для тестирования различных приложений (без покупки доменного имени) необходимо:
	вариант 1:
		в Windows внести изменения в файл hosts - C:\Windows\System32\drivers\etc\hosts
			82.165.178.140 sub1.koloboks.de		...приложение на хосте /var/www/html
			82.165.178.140 sub2.koloboks.de		...приложение в контейнере
			82.165.178.140 vite.koloboks.de		...приложение на хосте /var/www/html
		выполнить очистку кэша DNS с помощью команды 
			>ipconfig /flushdns
			>sudo systemctl restart nginx
	вариант 2:
		или регистрировать на strato каждый субдомен для koloboks.de с DNS A record IP-сервера
			sub1.koloboks.de, sub2.koloboks.de, vite.koloboks.de

# https для *.koloboks.de
установлена DNS TXT record для certbot certonly --manual 			