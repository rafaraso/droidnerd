Depois de muitas de horas de frustração, consegui configurar um ambiente que é, no mínimo, muito interessante para ser utilizado como uma plataforma alternativa de blog muito estilosa! Logo, tentarei replicar de forma sucinta os passos necessários para a configuração de um blog movido a **Jekyll + GitHub**.

Este tutorial tem como foco a plataforma **Windows**. Porém, para o funcionamento adequado do Jekyll, farei uso de uma VM com Linux.

**CONTEÚDO:**

1. Considerações iniciais
2. Preparando a máquina virtual
   * Por que Lubuntu?
   * VirtualBox Guest Additions
   * Sublime Text 3
   * Pasta compartilhada entre Windows e Linux
3. Instalando o essencial
   * Ruby + Dependências
   * GitHub SSH Key
   * Jekyll
4. Direto ao assunto
   * Fork no tema Minimal Mistakes
   * Clonando o repositório
   * Jekyll no modo desenvolvimento
5. Conteúdo adicional

&nbsp;  

## Considerações iniciais
&nbsp;  

![Octojekyll](../images/octojekyll.png){: .align-left}
Para seguir este tutorial, é necessário ter conhecimentos básicos sobre [Git](https://git-scm.com/), Linux Shell, HTML, CSS, JavaScript, etc. Bem como, possuir o [VirtualBox](https://www.virtualbox.org/wiki/Downloads) instalado.

&nbsp;  

## Preparando a máquina virtual
&nbsp;


![Lubuntu](../images/lubuntu-logo.png){: .align-left}
**Por que Lubuntu?**  
Bom, como eu não sou nenhum pica das Arábias em Linux, do tipo que usa distribuições em modo CLI e só precisa do [VIM](http://www.vim.org/) para editar até mesmo a própia vida, escolhi o Lubuntu por ocupar uma memória adicional irrisória em relação ao Debian + LXDE e apresentar uma perfomance gráfica *out-of-the-box* superior.

A instalação do Lubuntu é bastante simples, sem nada a ser considerado, exceto o layout do teclado. Se você, assim como eu, possui um teclado americano e precisa de alguns caracteres especiais como o *ç*, lembre-se que o Layout é o **US - alt-intl** e a maneira de utilizá-los pode ou não ser diferente em relação ao Windows.

Instale o Lubuntu baixando o .iso correspondete à sua arquitetura, criando uma nova VM no VirtualBox de acordo com suas preferências pessoais 
(deixei a minha com 2GB de RAM) e emule a imagem assim que inicia-lá. Lembrando que é uma boa prática deixar o adaptor de rede em modo bridge.

Para encerrar este tópico, adiciono às vantagens óbvias do Lubuntu, dentre as várias *lightweight Linux distros*, o ilustre (newby friendly) APT. 

[Vá baixar o lubuntu!](http://lubuntu.net/){: .btn .btn--x-large .btn--info}

**VirtualBox Guest Additions**

No intuito de manter um blog totalmente personalizável, com todas as suas ferramentas de construção funcionando com perfeição, editando imagens como qualquer profissional que se preze, a transição de conteúdo da área de transferência entre a máquina hospedeira e a convidada, ou vice-versa, é essencial. Em outras palavras, o Guest Additions fará  com que o famoso **`Ctrl+c/Ctrl+v`** funcione a todo vapor!

A fim de evitar qualquer tipo de surpresa durante a instalação, execute os comandos:

{% highlight bash %}
   sudo su;
   apt-get update;
   apt-get install build-essential module-assistant;
   m-a prepare;
{% endhighlight %}

Clique em **`Devices -> Insert Guest Additions CD Image`** e então execute:

{% highlight bash %}
   sh /media/cdrom/VBoxLinuxAdditions.run
{% endhighlight %}

&nbsp;

![Sublime Text](../images/logo-sublime-text.png){: .align-right}
**Sublime Text 3**

Sem a necessidade de qualquer IDE pesada e lenta, o Sublime Text é ideal para a manutenção de projetos deste tipo.
:thumbsup: :thumbsup: :thumbsup:

A instalação do Sublime é bem simples:

{% highlight bash %}
   sudo su;
   add-apt-repository ppa:webupd8team/sublime-text-3;
   apt-get update;
   apt-get install sublime-text-installer;
{% endhighlight %}

Depois de instalado o Sublime Text 3 terá como link simbólico o `subl`. Se preferir, você pode adicionar o `sublime`:

{% highlight bash %}
   sudo ln -s /opt/sublime_text/sublime_text /usr/bin/sublime
{% endhighlight %}

Para desinstalar:
sudo apt-get remove --auto-remove sublime-text-installer
sudo apt-get purge --auto-remove sublime-text-installer 

Caso tenha problemas de acesso
cd ~/.config
sudo chown -R developer:developer sublime-text-3

cd /opt
sudo chown -R developer:developer sublime_text

blabla


fffff



