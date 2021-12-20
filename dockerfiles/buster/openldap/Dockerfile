FROM debian:buster-slim

ARG OPENLDAP_PACKAGE_VERSION=2.4.57

ARG LDAP_OPENLDAP_GID
ARG LDAP_OPENLDAP_UID

ARG PQCHECKER_VERSION=2.0.0
ARG PQCHECKER_MD5=c005ce596e97d13e39485e711dcbc7e1

# Add openldap user and group first to make sure their IDs get assigned consistently, regardless of whatever dependencies get added
# If explicit uid or gid is given, use it.
RUN if [ -z "${LDAP_OPENLDAP_GID}" ]; then groupadd -g 911 -r openldap; else groupadd -r -g ${LDAP_OPENLDAP_GID} openldap; fi \
    && if [ -z "${LDAP_OPENLDAP_UID}" ]; then useradd -u 911 -r -g openldap openldap; else useradd -r -g openldap -u ${LDAP_OPENLDAP_UID} openldap; fi