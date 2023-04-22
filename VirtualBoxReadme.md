# VirtualBox Shortcuts

1. Host key + Home => Takes you to the top of the VM's console window.

2. Host key + End => Takes you to the bottom of the VM's console window.

3. Host key + F => Switches the VM to full screen mode.

4. Host key + C => Captures the keyboard and mouse input to the VM.

5. Host key + L => Switches the VM to seamless mode.

6. Host key + P => Pauses the VM.

7. Host key + R => Resets the VM.

8. Host key + S => Saves the state of the VM.

9. Host key + F1 => Opens the Oracle VM VirtualBox help file.

10. Host key + F2 => Shows or hides the menu bar of the Oracle VM VirtualBox Manager.

Note: The Host key is usually the right Ctrl key on most keyboards, but this can be customized in the settings.

### Copiando arquivos do Windows para o UbuntuServer dentro do VirtualBox

Primeiro, certifique-se de que você tem o VirtualBox Guest Additions instalado na sua máquina virtual Ubuntu. Isso permitirá que você compartilhe pastas entre o host (Windows) e a máquina virtual (Ubuntu).

Depois de ter o Guest Additions instalado, inicie a máquina virtual e faça login no Ubuntu.

Clique em configurações (engrenagem) da sua imagem montada e em seguida em "Pastas Compartilhadas". Clique em "Adicionar pasta compartilhada" e escolha a pasta no seu host (Windows) que contém o arquivo que você deseja copiar. Certifique-se de marcar a opção "Montar automaticamente" e clique em "OK".

No Ubuntu, crie uma pasta em algum lugar onde você queira armazenar o arquivo copiado.

Monte a pasta compartilhada do Windows na pasta que você acabou de criar no Ubuntu, usando o seguinte comando:

sudo mount -t vboxsf nome_da_pasta_compartilhada /endereco_de_destino

Pronto, sua máquina virtual agora tem acesso a todos os arquivos que estão dentro da pasta compartilhada.
