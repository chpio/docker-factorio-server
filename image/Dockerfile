FROM chpio/gosu:jessie

RUN { set -ex; \
	VERSION="0.12.33"; \

	# create user
	groupadd --gid 1000 -r factorio; \
	useradd --uid 1000 -r -g factorio factorio; \

	BUILD_DEPS="curl ca-certificates"; \
	apt-get update; \
	apt-get install --no-install-recommends -y $BUILD_DEPS; \

	# download
	cd /tmp; \
	curl -fsSL "https://www.factorio.com/get-download/$VERSION/headless/linux64" | tar -xzf -; \

	# install
	cd /tmp/factorio; \
	mv bin/x64/factorio /usr/bin; \
	mkdir -p /opt/factorio; \
	mv data /opt/factorio/data; \

	# clean up
	apt-get purge -y $BUILD_DEPS; \
	apt-get autoremove --purge -y; \
	rm -rf /var/lib/apt/lists/* /tmp/*; \
}

VOLUME ["/data/factorio"]

COPY config.ini /opt/factorio

COPY start-factorio /usr/bin
ENTRYPOINT ["start-factorio"]
