# CS252-P2P-File-Transfer

## Overview of the project

The following objectives have been achieved as a part of the project:

There is a network of clients which are interconnected with each other based on a
specified topology.

● A client (which you will code) will be provided with the following information as
arguments. Note the same client code will be run multiple times with different arguments
to mimic different clients.

  ○ A directory path: this is specific to this client. The client is the owner of all files
  present in that directory. Another client may be searching for these files to
  download.
  
  ○ A path to a configuration file, which will include the following
  
    ■ Client ID and port on which it is ready to listen for incoming connections
    
    ■ A list of immediate neighbors and the ports they are listening on. The
    client is supposed to have direct connections with these neighbors for
    search purposes.
    
    ■ A list of files which the client should search for in the network. These files
    the client does not possess originally, hence it wants to search and finally
    download them. The downloaded files should be stored in the above
    mentioned directory path under a folder “Downloaded”. These files should
    NOT be made available to others who are searching ,since this client is not
    the owner.
    
● Each of the n clients upon initialization should process its arguments; setup connections
with its immediate neighbors and print relevant output (see details below).

● After this, each client should search for certain files as specified in the configuration file.
It can search only upto a specified depth d. For example d==2 means, it will search
clients upto 2 hops away from it.

● If a file is found at another client, it should setup a separate tcp connection (if not already
present) with that client and receive the file. After reception, this connection must be
closed. Note File search should happen only via the initial connections specified
