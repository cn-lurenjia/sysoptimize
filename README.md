#!/bin/bash
#
echo 50000 > /proc/sys/net/core/somaxconn
echo 1 > /proc/sys/net/ipv4/tcp_tw_recycle
echo 1 > /proc/sys/net/ipv4/tcp_tw_reuse
echo 0 > /proc/sys/net/ipv4/tcp_syncookies
ulimit -n 50000
echo "* hard nofile 50000" >> /etc/security/limits.conf
echo "* soft nofile 50000" >> /etc/security/limits.conf
echo "* hard noproc 50000" >> /etc/security/limits.conf
echo "* soft noproc 50000" >> /etc/security/limits.conf
