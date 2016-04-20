# glb

import ftplib
server = 'ftp.themillerline.com'
username = 'username'
password = 'password'
ftp_connection = ftplib.FTP(server, username, password)
remote_path = '/public_html/glb/'
change_path = '/public_html/glb/pages/'


ftp_connection.cwd(remote_path)
ftp_connection.rename ('index.html', 'zindex.html')
ftp_connection.rename ('overall.html', 'zoverall.html')
ftp_connection.rename ('wild.html', 'zwild.html')
fi = open('index.html', 'rb')
ftp_connection.storbinary('STOR index.html', fi)
fi.close()
print ('index loaded')
fo = open('overall.html', 'rb')
ftp_connection.storbinary('STOR overall.html', fo)
fo.close()
print ('overall loaded')
fw = open('wild.html', 'rb')
ftp_connection.storbinary('STOR wild.html', fw)
fw.close()	
print ('wild loaded')
