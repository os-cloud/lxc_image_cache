LXC image index creator
#######################
:tags: repo, server, cloud, ansible, lxc, cache, image
:category: \*nix

Deploy and create an LXC image and deploy it onto an index

.. code-block:: yaml

    - name: Create an LXC image index
      hosts: 127.0.0.1
      user: root
      roles:
        - role: "lxc_image_cache"
          lxc_image_compression: 0
          lxc_image_tag: untagged
          lxc_image_folder: /var/www
          lxc_image_cache_base_container_destroy: true
          lxc_image_cache_index_create: true
          lxc_image_cache_create: true
          lxc_image_cache_host_preload: false
          tags:
            - "lxc-image-index"


Pre-load the host cache with an LXC container image

.. code-block:: yaml

    - name: Create an LXC image index
      hosts: 127.0.0.1
      user: root
      roles:
        - role: "lxc_image_cache"
          lxc_image_compression: 0
          lxc_image_tag: untagged
          lxc_image_folder: /var/www
          lxc_image_cache_base_container_destroy: true
          lxc_image_cache_index_create: false
          lxc_image_cache_create: false
          lxc_image_cache_host_preload: true
          tags:
            - "lxc-image-index"
