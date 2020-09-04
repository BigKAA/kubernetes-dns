# kubernetes-dns
_Если бы я был абсолютным злом, я бы сломал DNS по всему миру,
взял попкорн и стал набладать за тем как вы мучитесь._

Все примеры будут запускаться в namespace default 

Для проверки работы DNS будем использовать образ 
infoblox/dnstools:

    kubectl run -it --rm --restart=Never --image=infoblox/dnstools:latest dnstools

Запуск программ на конктретной ноде:

    kubectl run -it --rm --restart=Never --image=infoblox/dnstools:latest dnstools \
    --overrides='{"apiVersion": "v1", "spec": {"nodeSelector": { "kubernetes.io/hostname": "node1.kryukov.local" }}}'
