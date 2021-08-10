# Third-party hosting

A **third-party host** is an individual or a business which **self-hosts a BTCPay Server instance and enables other users to register and use the server**. On a self-hosted server, the owner can add an unlimited amount of users and stores and allow those users to manage their stores independently and receive payments to their own wallets.

While this feature in BTCPay Server exists for complex multi-store business management, community enthusiasts use it to help other users (mostly beginners), sometimes skip an overwhelming step of **deploying a self-hosted BTCPay server**. Users who want to test or develop applications on top of BTCPay Server also use **instances hosted by third-parties**. Some hosts try to spread the adoption of cryptocurrencies by allowing their local merchants to receive payments for free or for a small sign-up fee.

In layman words, think of this feature as a payment processor factory which allows anyone to deploy a server and help others receive payments which are validated via the server owners' [full Bitcoin node](https://en.bitcoin.it/wiki/Full_node).

**Third-party hosts** play an important role in the ecosystem since they provide an easy and cost-effective **way for users to try and use BTCPay Server**. The role of honest hosts who provide free service to others is essential in the early phase of BTCPay Server adoption. However, users should be familiar with the pros, cons and potential risks involved when using a trusted third-party. Find the optimal balance between your use-case, cost, and privacy/security trade-offs.

Some of the hosts are entirely free to use and maintain the server cost from donations of their users. If you've been using a reliable free host for a while, you should consider donating to them to support them.

- [Third-party hosting](#third-party-hosting)
  - [Advantages and disadvantages](#advantages-and-disadvantages)
    - [Pros](#pros)
    - [Cons](#cons)
  - [Concerns For Use](#concerns-for-use)
    - [Security Concerns](#security-concerns)
    - [Privacy Concerns](#privacy-concerns)
    - [Trust Concerns](#trust-concerns)
  - [Third Party Hosting FAQ](#third-party-hosting-faq)
  - [Where is the list of BTCPay third-party hosts?](#where-is-the-list-of-btcpay-third-party-hosts)
  - [How can one become a third-party host?](#how-can-one-become-a-third-party-host)
  - [Are there any limitations in features when using a third-party host?](#are-there-any-limitations-in-features-when-using-a-third-party-host)
  - [Can I enable the use of my Lightning Network node to others?](#can-i-enable-the-use-of-my-lightning-network-node-to-others)
  - [What does the trusted third-party host know about their users?](#what-does-the-trusted-third-party-host-know-about-their-users)

## Advantages and disadvantages

### Pros
* Easy and quicker setup
* Cheaper and in most cases free (depending if the host is premium or free)
* Receive payments directly to your wallet
* Private key never required (if it is, it's a scam!)

### Cons
* Security concerns
* Privacy concerns
* Limitation of features
* No control over a server
* Have to trust the owner of the server

## Concerns For Use

### Security Concerns
[Trusted third parties are security holes](https://nakamotoinstitute.org/trusted-third-parties/#selection-7.6-6.2). By relying on someone else to manage a server for you, you are potentially exposing yourself to a certain attack vector.

The most significant attack vector when using a third-party host is the chance that this host will gain access to the management of your funds. This can occur in two ways.

First, a host may allow you to create [hot wallets](https://en.bitcoin.it/wiki/Hot_wallet) on their server. This gives the host complete access to your funds. They will act as a custodian of your private keys and thus your funds. This means you must trust they will not spend your funds. This type of wallet is NOT recommended for use with third-party hosts.

Secondly, a malicious and technically skilled host can create a forked version of BTCPay Server and modify it to be able to either spy on your transactions or replace your [extended public key](https://en.bitcoin.it/wiki/Deterministic_wallet_tools#Risks_of_Sharing_an_Extended_Public_Key_.28xpub.29) with their own. This means that future payments made to you may end up in this malicious party's wallet. 

While a wallet connected with an extended public key IS recommended for use with third-party hosts, It's impossible to know for certain, if the third party host is using a malicious fork. If you don't trust the third party host it is best to do the following:

- Do not use hot wallet on the third party server, use an extended public key
- Use it mainly for testing, learning and getting started with BTCPay
- Do not use it with high volume payments or extremely valuable transactions 

In BTCPay Server, a private key is never *required*. This means that funds are safe even if the server is hacked, but a malicious host can intercept future payments and steal those funds. If you follow your transactions via a watch-only wallet, you should be able to detect such attack quickly and notice that your orders are being marked as paid, whereas you don't see the transactions in your wallet.

:::danger
If a third-party host asks for your private key or pre-generates one for you, be sure it's a scam. Never share your private key with anyone. It's called private for a reason.
:::

An extended public key replacement attack applies to a self-hosted server as well. A malicious hacker can try to hack your server and try to replace an extended public key.

### Privacy Concerns
BTCPay Server does not allow server hosts to view the stores of other users nor have access to any personal data (except for registration email address). The extended public key and even balances of other users can't be seen. However, as mentioned, a malicious third-party could modify that by creating a fork that can look like BTCPay Server on the front but be something completely different in reality.

The biggest concern, which happens when using a third-party host (even if the owner of a self-hosted server is not malicious) comes from the nature of the Bitcoin itself. If a user is not running a full node but instead relies on someone else's node, his transactions can be listened to by the owner of that node. Running a full node is not just a convenience that gives you features and enables privacy, it gives you better security and the right to "vote" and validate all the transactions yourself. Don't trust, verify.

Here are some good resources where you learn more about the importance of full nodes

* [Why Your Business Should Use a Full Node to Accept Bitcoin](https://en.bitcoin.it/wiki/Why_Your_Business_Should_Use_a_Full_Node_to_Accept_Bitcoin)
* [Clearing Up Misconceptions About Full Nodes](https://en.bitcoin.it/wiki/Clearing_Up_Misconceptions_About_Full_Nodes)

### Trust Concerns
Third-party hosts have the ability to enable specific features for their non-admin users which require users to place some level of trust in the third-party host, if such features are used.

Specifically, third-party hosts should not enable the following policies without understanding that users will be using hot wallets on the server. These features are disabled by default for non-admins to reduce the risk considerations for both third-party hosts and their users:

- Allow non-admins to create hot wallets for their stores
- Allow non-admins to import their hot wallets to the node wallet
- Allow non-admins to use the internal lightning node in their stores

Third-party users who are granted access to an internal lightning node or hot wallet functionality to enable features such as Payjoin, should understand the risk and trust associated with [using hot wallets](./CreateWallet.md#hot-wallet) before choosing to use it. Use one of the [recommended wallets](./WalletSetup.md) which provide an extended public key to use in your store, if you are unsure which wallet type to use.

## Third Party Hosting FAQ

## Where is the list of BTCPay third-party hosts?

Feel free to chat with the [Community](./Community.md) to find the appropriate host for your needs, but also make sure to choose one that is trustworthy. Read the rest of this document to better understand the pros and cons of using a third-party host.

:::tip
The BTCPay Server [Directory](https://directory.btcpayserver.org/filter/hosts) lists multiple free or paid third-party hosts that you can register to, to start exploring BTCPay Server.
:::

## How can one become a third-party host?
To become a third-party host, you need to self-host a BTCPay Server and enable registration for other users.
Go to Server Settings > Policies > Disable registration, unmark the checkbox. You may also want to configure the [SMTP settings](./FAQ/FAQ-ServerSettings.md#how-to-configure-smtp-settings-in-btcpay) to allow them to reset their password if they forget it.

Alternatively you may keep public registration disabled on your homepage and only invite specific users to create a new account by [invitation link](./FAQ/FAQ-ServerSettings.md#how-to-add-a-new-user-by-invite).

## Are there any limitations in features when using a third-party host?
Yes. Here are some restrictions.
* No [Lightning Network](./LightningNetwork.md) by default. Can be enabled by the third-party host but at the cost of a security risk for registrants using that third-party. [More information](#can-i-enable-the-use-of-my-lightning-network-node-to-others)
* No [wallet re-scan](./FAQ/FAQ-Wallet.md#what-is-wallet-re-scan-in-btcpay)
* No [Server Settings](./Walkthrough.md#server-settings) access

The limitations happen for technical reasons, mostly because these features require a user to run a full node to use them.

## Can I enable the use of my Lightning Network node to others?

Yes, you can enable users that have registered on your BTCPay Server instance to use your Lightning Network node.
[See how](./FAQ/FAQ-LightningNetwork.md#how-many-users-can-use-lightning-network-in-btcpay)

## What does the trusted third-party host know about their users?
Third party hosts (non-malicious) can see the following:

- Total number of users
- The email and username of those users

Note: If additional features are enabled such as non-admin lightning wallet, hot wallets or transmuter, the server admin can see additional information related to those features. Since it's impossible to know if the third party host is using a malicious fork, it's best to assume they may know all details about your BTCPay Server usage.

If you are worried about the information a third party host knows about you, please consider [deploying your own](./Deployment.md) self-hosted server.

  ]
   {
       #!/bin/sh
# install - install a program, script, or datafile

scriptversion=2011-11-20.07; # UTC

# This originates from X11R5 (mit/util/scripts/install.sh), which was
# later released in X11R6 (xc/config/util/install.sh) with the
# following copyright and license.
#
# Copyright (C) 1994 X Consortium
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to
# deal in the Software without restriction, including without limitation the
# rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
# sell copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
# X CONSORTIUM BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
# AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNEC-
# TION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
#
# Except as contained in this notice, the name of the X Consortium shall not
# be used in advertising or otherwise to promote the sale, use or other deal-
# ings in this Software without prior written authorization from the X Consor-
# tium.
#
#
# FSF changes to this file are in the public domain.
#
# Calling this script install-sh is preferred over install.sh, to prevent
# 'make' implicit rules from creating a file called install from it
# when there is no Makefile.
#
# This script is compatible with the BSD install script, but was written
# from scratch.

nl='
'
IFS=" ""	$nl"

# set DOITPROG to echo to test this script

# Don't use :- since 4.3BSD and earlier shells don't like it.
doit=${DOITPROG-}
if test -z "$doit"; then
  doit_exec=exec
else
  doit_exec=$doit
fi

# Put in absolute file names if you don't have them in your path;
# or use environment vars.

chgrpprog=${CHGRPPROG-chgrp}
chmodprog=${CHMODPROG-chmod}
chownprog=${CHOWNPROG-chown}
cmpprog=${CMPPROG-cmp}
cpprog=${CPPROG-cp}
mkdirprog=${MKDIRPROG-mkdir}
mvprog=${MVPROG-mv}
rmprog=${RMPROG-rm}
stripprog=${STRIPPROG-strip}

posix_glob='?'
initialize_posix_glob='
  test "$posix_glob" != "?" || {
    if (set -f) 2>/dev/null; then
      posix_glob=
    else
      posix_glob=:
    fi
  }
'

posix_mkdir=

# Desired mode of installed file.
mode=0755

chgrpcmd=
chmodcmd=$chmodprog
chowncmd=
mvcmd=$mvprog
rmcmd="$rmprog -f"
stripcmd=

src=
dst=
dir_arg=
dst_arg=

copy_on_change=false
no_target_directory=

usage="\
Usage: $0 [OPTION]... [-T] SRCFILE DSTFILE
   or: $0 [OPTION]... SRCFILES... DIRECTORY
   or: $0 [OPTION]... -t DIRECTORY SRCFILES...
   or: $0 [OPTION]... -d DIRECTORIES...

In the 1st form, copy SRCFILE to DSTFILE.
In the 2nd and 3rd, copy all SRCFILES to DIRECTORY.
In the 4th, create DIRECTORIES.

Options:
     --help     display this help and exit.
     --version  display version info and exit.

  -c            (ignored)
  -C            install only if different (preserve the last data modification time)
  -d            create directories instead of installing files.
  -g GROUP      $chgrpprog installed files to GROUP.
  -m MODE       $chmodprog installed files to MODE.
  -o USER       $chownprog installed files to USER.
  -s            $stripprog installed files.
  -t DIRECTORY  install into DIRECTORY.
  -T            report an error if DSTFILE is a directory.

Environment variables override the default commands:
  CHGRPPROG CHMODPROG CHOWNPROG CMPPROG CPPROG MKDIRPROG MVPROG
  RMPROG STRIPPROG
"

while test $# -ne 0; do
  case $1 in
    -c) ;;

    -C) copy_on_change=true;;

    -d) dir_arg=true;;

    -g) chgrpcmd="$chgrpprog $2"
	shift;;

    --help) echo "$usage"; exit $?;;

    -m) mode=$2
	case $mode in
	  *' '* | *'	'* | *'
'*	  | *'*'* | *'?'* | *'['*)
	    echo "$0: invalid mode: $mode" >&2
	    exit 1;;
	esac
	shift;;

    -o) chowncmd="$chownprog $2"
	shift;;

    -s) stripcmd=$stripprog;;

    -t) dst_arg=$2
	# Protect names problematic for 'test' and other utilities.
	case $dst_arg in
	  -* | [=\(\)!]) dst_arg=./$dst_arg;;
	esac
	shift;;

    -T) no_target_directory=true;;

    --version) echo "$0 $scriptversion"; exit $?;;

    --)	shift
	break;;

    -*)	echo "$0: invalid option: $1" >&2
	exit 1;;

    *)  break;;
  esac
  shift
done

if test $# -ne 0 && test -z "$dir_arg$dst_arg"; then
  # When -d is used, all remaining arguments are directories to create.
  # When -t is used, the destination is already specified.
  # Otherwise, the last argument is the destination.  Remove it from $@.
  for arg
  do
    if test -n "$dst_arg"; then
      # $@ is not empty: it contains at least $arg.
      set fnord "$@" "$dst_arg"
      shift # fnord
    fi
    shift # arg
    dst_arg=$arg
    # Protect names problematic for 'test' and other utilities.
    case $dst_arg in
      -* | [=\(\)!]) dst_arg=./$dst_arg;;
    esac
  done
fi

if test $# -eq 0; then
  if test -z "$dir_arg"; then
    echo "$0: no input file specified." >&2
    exit 1
  fi
  # It's OK to call 'install-sh -d' without argument.
  # This can happen when creating conditional directories.
  exit 0
fi

if test -z "$dir_arg"; then
  do_exit='(exit $ret); exit $ret'
  trap "ret=129; $do_exit" 1
  trap "ret=130; $do_exit" 2
  trap "ret=141; $do_exit" 13
  trap "ret=143; $do_exit" 15

  # Set umask so as not to create temps with too-generous modes.
  # However, 'strip' requires both read and write access to temps.
  case $mode in
    # Optimize common cases.
    *644) cp_umask=133;;
    *755) cp_umask=22;;

    *[0-7])
      if test -z "$stripcmd"; then
	u_plus_rw=
      else
	u_plus_rw='% 200'
      fi
      cp_umask=`expr '(' 777 - $mode % 1000 ')' $u_plus_rw`;;
    *)
      if test -z "$stripcmd"; then
	u_plus_rw=
      else
	u_plus_rw=,u+rw
      fi
      cp_umask=$mode$u_plus_rw;;
  esac
fi

for src
do
  # Protect names problematic for 'test' and other utilities.
  case $src in
    -* | [=\(\)!]) src=./$src;;
  esac

  if test -n "$dir_arg"; then
    dst=$src
    dstdir=$dst
    test -d "$dstdir"
    dstdir_status=$?
  else

    # Waiting for this to be detected by the "$cpprog $src $dsttmp" command
    # might cause directories to be created, which would be especially bad
    # if $src (and thus $dsttmp) contains '*'.
    if test ! -f "$src" && test ! -d "$src"; then
      echo "$0: $src does not exist." >&2
      exit 1
    fi

    if test -z "$dst_arg"; then
      echo "$0: no destination specified." >&2
      exit 1
    fi
    dst=$dst_arg

    # If destination is a directory, append the input filename; won't work
    # if double slashes aren't ignored.
    if test -d "$dst"; then
      if test -n "$no_target_directory"; then
	echo "$0: $dst_arg: Is a directory" >&2
	exit 1
      fi
      dstdir=$dst
      dst=$dstdir/`basename "$src"`
      dstdir_status=0
    else
      # Prefer dirname, but fall back on a substitute if dirname fails.
      dstdir=`
	(dirname "$dst") 2>/dev/null ||
	expr X"$dst" : 'X\(.*[^/]\)//*[^/][^/]*/*$' \| \
	     X"$dst" : 'X\(//\)[^/]' \| \
	     X"$dst" : 'X\(//\)$' \| \
	     X"$dst" : 'X\(/\)' \| . 2>/dev/null ||
	echo X"$dst" |
	    sed '/^X\(.*[^/]\)\/\/*[^/][^/]*\/*$/{
		   s//\1/
		   q
		 }
		 /^X\(\/\/\)[^/].*/{
		   s//\1/
		   q
		 }
		 /^X\(\/\/\)$/{
		   s//\1/
		   q
		 }
		 /^X\(\/\).*/{
		   s//\1/
		   q
		 }
		 s/.*/./; q'
      `

      test -d "$dstdir"
      dstdir_status=$?
    fi
  fi

  obsolete_mkdir_used=false

  if test $dstdir_status != 0; then
    case $posix_mkdir in
      '')
	# Create intermediate dirs using mode 755 as modified by the umask.
	# This is like FreeBSD 'install' as of 1997-10-28.
	umask=`umask`
	case $stripcmd.$umask in
	  # Optimize common cases.
	  *[2367][2367]) mkdir_umask=$umask;;
	  .*0[02][02] | .[02][02] | .[02]) mkdir_umask=22;;

	  *[0-7])
	    mkdir_umask=`expr $umask + 22 \
	      - $umask % 100 % 40 + $umask % 20 \
	      - $umask % 10 % 4 + $umask % 2
	    `;;
	  *) mkdir_umask=$umask,go-w;;
	esac

	# With -d, create the new directory with the user-specified mode.
	# Otherwise, rely on $mkdir_umask.
	if test -n "$dir_arg"; then
	  mkdir_mode=-m$mode
	else
	  mkdir_mode=
	fi

	posix_mkdir=false
	case $umask in
	  *[123567][0-7][0-7])
	    # POSIX mkdir -p sets u+wx bits regardless of umask, which
	    # is incompatible with FreeBSD 'install' when (umask & 300) != 0.
	    ;;
	  *)
	    tmpdir=${TMPDIR-/tmp}/ins$RANDOM-$$
	    trap 'ret=$?; rmdir "$tmpdir/d" "$tmpdir" 2>/dev/null; exit $ret' 0

	    if (umask $mkdir_umask &&
		exec $mkdirprog $mkdir_mode -p -- "$tmpdir/d") >/dev/null 2>&1
	    then
	      if test -z "$dir_arg" || {
		   # Check for POSIX incompatibilities with -m.
		   # HP-UX 11.23 and IRIX 6.5 mkdir -m -p sets group- or
		   # other-writable bit of parent directory when it shouldn't.
		   # FreeBSD 6.1 mkdir -m -p sets mode of existing directory.
		   ls_ld_tmpdir=`ls -ld "$tmpdir"`
		   case $ls_ld_tmpdir in
		     d????-?r-*) different_mode=700;;
		     d????-?--*) different_mode=755;;
		     *) false;;
		   esac &&
		   $mkdirprog -m$different_mode -p -- "$tmpdir" && {
		     ls_ld_tmpdir_1=`ls -ld "$tmpdir"`
		     test "$ls_ld_tmpdir" = "$ls_ld_tmpdir_1"
		   }
		 }
	      then posix_mkdir=:
	      fi
	      rmdir "$tmpdir/d" "$tmpdir"
	    else
	      # Remove any dirs left behind by ancient mkdir implementations.
	      rmdir ./$mkdir_mode ./-p ./-- 2>/dev/null
	    fi
	    trap '' 0;;
	esac;;
    esac

    if
      $posix_mkdir && (
	umask $mkdir_umask &&
	$doit_exec $mkdirprog $mkdir_mode -p -- "$dstdir"
      )
    then :
    else

      # The umask is ridiculous, or mkdir does not conform to POSIX,
      # or it failed possibly due to a race condition.  Create the
      # directory the slow way, step by step, checking for races as we go.

      case $dstdir in
	/*) prefix='/';;
	[-=\(\)!]*) prefix='./';;
	*)  prefix='';;
      esac

      eval "$initialize_posix_glob"

      oIFS=$IFS
      IFS=/
      $posix_glob set -f
      set fnord $dstdir
      shift
      $posix_glob set +f
      IFS=$oIFS

      prefixes=

      for d
      do
	test X"$d" = X && continue

	prefix=$prefix$d
	if test -d "$prefix"; then
	  prefixes=
	else
	  if $posix_mkdir; then
	    (umask=$mkdir_umask &&
	     $doit_exec $mkdirprog $mkdir_mode -p -- "$dstdir") && break
	    # Don't fail if two instances are running concurrently.
	    test -d "$prefix" || exit 1
	  else
	    case $prefix in
	      *\'*) qprefix=`echo "$prefix" | sed "s/'/'\\\\\\\\''/g"`;;
	      *) qprefix=$prefix;;
	    esac
	    prefixes="$prefixes '$qprefix'"
	  fi
	fi
	prefix=$prefix/
      done

      if test -n "$prefixes"; then
	# Don't fail if two instances are running concurrently.
	(umask $mkdir_umask &&
	 eval "\$doit_exec \$mkdirprog $prefixes") ||
	  test -d "$dstdir" || exit 1
	obsolete_mkdir_used=true
      fi
    fi
  fi

  if test -n "$dir_arg"; then
    { test -z "$chowncmd" || $doit $chowncmd "$dst"; } &&
    { test -z "$chgrpcmd" || $doit $chgrpcmd "$dst"; } &&
    { test "$obsolete_mkdir_used$chowncmd$chgrpcmd" = false ||
      test -z "$chmodcmd" || $doit $chmodcmd $mode "$dst"; } || exit 1
  else

    # Make a couple of temp file names in the proper directory.
    dsttmp=$dstdir/_inst.$$_
    rmtmp=$dstdir/_rm.$$_

    # Trap to clean up those temp files at exit.
    trap 'ret=$?; rm -f "$dsttmp" "$rmtmp" && exit $ret' 0

    # Copy the file name to the temp name.
    (umask $cp_umask && $doit_exec $cpprog "$src" "$dsttmp") &&

    # and set any options; do chmod last to preserve setuid bits.
    #
    # If any of these fail, we abort the whole thing.  If we want to
    # ignore errors from any of these, just make sure not to ignore
    # errors from the above "$doit $cpprog $src $dsttmp" command.
    #
    { test -z "$chowncmd" || $doit $chowncmd "$dsttmp"; } &&
    { test -z "$chgrpcmd" || $doit $chgrpcmd "$dsttmp"; } &&
    { test -z "$stripcmd" || $doit $stripcmd "$dsttmp"; } &&
    { test -z "$chmodcmd" || $doit $chmodcmd $mode "$dsttmp"; } &&

    # If -C, don't bother to copy if it wouldn't change the file.
    if $copy_on_change &&
       old=`LC_ALL=C ls -dlL "$dst"	2>/dev/null` &&
       new=`LC_ALL=C ls -dlL "$dsttmp"	2>/dev/null` &&

       eval "$initialize_posix_glob" &&
       $posix_glob set -f &&
       set X $old && old=:$2:$4:$5:$6 &&
       set X $new && new=:$2:$4:$5:$6 &&
       $posix_glob set +f &&

       test "$old" = "$new" &&
       $cmpprog "$dst" "$dsttmp" >/dev/null 2>&1
    then
      rm -f "$dsttmp"
    else
      # Rename the file to the real destination.
      $doit $mvcmd -f "$dsttmp" "$dst" 2>/dev/null ||

      # The rename failed, perhaps because mv can't rename something else
      # to itself, or perhaps because mv is so ancient that it does not
      # support -f.
      {
	# Now remove or move aside any old file at destination location.
	# We try this two ways since rm can't unlink itself on some
	# systems and the destination file might be busy for other
	# reasons.  In this case, the final cleanup might fail but the new
	# file should still install successfully.
	{
	  test ! -f "$dst" ||
	  $doit $rmcmd -f "$dst" 2>/dev/null ||
	  { $doit $mvcmd -f "$dst" "$rmtmp" 2>/dev/null &&
	    { $doit $rmcmd -f "$rmtmp" 2>/dev/null; :; }
	  } ||
	  { echo "$0: cannot unlink or rename $dst" >&2
	    (exit 1); exit 1
	  }
	} &&

	# Now rename the file to the real destination.
	$doit $mvcmd "$dsttmp" "$dst"
      }
    fi || exit 1

    trap '' 0
  fi
done

# Local variables:
# eval: (add-hook 'write-file-hooks 'time-stamp)
# time-stamp-start: "scriptversion="
# time-stamp-format: "%:y-%02m-%02d.%02H"
# time-stamp-time-zone: "UTC"
# time-stamp-end: "; # UTC"
# End:
    
   }