NULL =

portal_files = 								\
	$(top_srcdir)/data/org.freedesktop.portal.Request.xml 		\
	$(top_srcdir)/data/org.freedesktop.portal.FileChooser.xml 	\
	$(top_srcdir)/data/org.freedesktop.portal.OpenURI.xml 		\
	$(top_srcdir)/data/org.freedesktop.portal.Print.xml 		\
	$(top_srcdir)/data/org.freedesktop.portal.Email.xml 		\
	$(top_srcdir)/data/org.freedesktop.portal.Screenshot.xml 	\
	$(top_srcdir)/data/org.freedesktop.portal.NetworkMonitor.xml 	\
	$(top_srcdir)/data/org.freedesktop.portal.ProxyResolver.xml 	\
	$(top_srcdir)/data/org.freedesktop.portal.Notification.xml 	\
	$(top_srcdir)/data/org.freedesktop.portal.Inhibit.xml	 	\
	$(top_srcdir)/data/org.freedesktop.portal.Device.xml	 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Request.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.FileChooser.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.AppChooser.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Print.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Email.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Screenshot.xml 	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Notification.xml	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Inhibit.xml	\
	$(top_srcdir)/data/org.freedesktop.impl.portal.Access.xml	\
	$(FLATPAK_INTERFACES_DIR)/org.freedesktop.portal.Documents.xml			\
	$(FLATPAK_INTERFACES_DIR)/org.freedesktop.impl.portal.PermissionStore.xml	\
	$(NULL)

xml_files = 								\
	portal-org.freedesktop.portal.Request.xml 			\
	portal-org.freedesktop.portal.FileChooser.xml 			\
	portal-org.freedesktop.portal.OpenURI.xml 			\
	portal-org.freedesktop.portal.Print.xml 			\
	portal-org.freedesktop.portal.Email.xml 			\
	portal-org.freedesktop.portal.Screenshot.xml 			\
	portal-org.freedesktop.portal.NetworkMonitor.xml		\
	portal-org.freedesktop.portal.ProxyResolver.xml			\
	portal-org.freedesktop.portal.Notification.xml			\
	portal-org.freedesktop.portal.Inhibit.xml			\
	portal-org.freedesktop.portal.Documents.xml			\
	portal-org.freedesktop.portal.Device.xml			\
	portal-org.freedesktop.impl.portal.Request.xml 			\
	portal-org.freedesktop.impl.portal.FileChooser.xml		\
	portal-org.freedesktop.impl.portal.AppChooser.xml 		\
	portal-org.freedesktop.impl.portal.Print.xml 			\
	portal-org.freedesktop.impl.portal.Email.xml 			\
	portal-org.freedesktop.impl.portal.Screenshot.xml 		\
	portal-org.freedesktop.impl.portal.Notification.xml 		\
	portal-org.freedesktop.impl.portal.Inhibit.xml	 		\
	portal-org.freedesktop.impl.portal.Access.xml	 		\
	portal-org.freedesktop.impl.portal.PermissionStore.xml		\
	$(NULL)

EXTRA_DIST = \
	docbook.css		\
	portal-docs.xml.in	\
	xmlto-config.xsl	\
	$(NULL)

$(xml_files) : $(portal_files)
	$(AM_V_GEN) $(GDBUS_CODEGEN) --generate-docbook portal $^

CLEANFILES =			\
	$(xml_files) 		\
	portal-docs.html	\
	$(NULL)

DISTCLEANFILES =	\
	portal-docs.xml	\
	$(NULL)

if DOCBOOK_DOCS_ENABLED

doc_DATA = 			\
	portal-docs.html	\
	docbook.css		\
	$(NULL)

portal-docs.html: portal-docs.xml $(xml_files) xmlto-config.xsl
	$(AM_V_GEN) $(XMLTO) $(XMLTO_FLAGS) xhtml-nochunks -m $(srcdir)/xmlto-config.xsl $<

endif # DOCBOOK_DOCS_ENABLED
