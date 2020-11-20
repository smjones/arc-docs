This section records the status of known implementations of [@RFC8617].

Please note that the listing of any
individual implementation here does not imply endorsement by the IETF.
Furthermore, no effort has been spent to verify the information presented here
that was supplied by IETF contributors.  This is not intended as, and must not
be construed to be, a catalog of available implementations or their features.
Readers are advised to note that other implementations may exist.

This information is known to be correct as of the ninth interoperability
test event which was held on 2018-10-12.

## GMail test reflector and incoming validation

   Organization: Google  
   Description: Internal production implementation with both debug
     analysis and validating + sealing pass-through function  
   Status of Operation: Production - Incoming Validation  
   Coverage: Full spec implemented 
   Licensing: Internal only  
   Implementation Notes:

  * Full functionality was demonstrated during the interop testing on 2018-03-17
    and 2018-10-12. All traffic going into GSuite, Google Groups, or GMail 
    mailboxes will have ARC validation and sealing. 

   Contact Info: <arc-discuss@dmarc.org>

## AOL test reflector and internal tagging

  Organization: AOL  
  Description: Internal prototype implementation with both debug
    analysis and validating + sealing pass-through function  
  Status of Operation: Obsolete
  Coverage: ARC Chain validity status checking is operational, but only
    applied to email addresses enrolled in the test program.
    This system conforms to ARC-DRAFT-05.
  Licensing: Proprietary - Internal only  
  Implementation Notes:

  * 2017-07-15: Full functionality verified during the interop testing.
  * 2018-06: Partially retired but still accessible by special request
  due to the in process evolution of the AOL mail infrastructure to the
  integrated OATH environment. The implementation was based on the Apache
  James DKIM code base.
  * 2018-10: No longer available due to infrastucture changes at
  AOL/Yahoo!/Oath.

  Contact Info: <arc-discuss@dmarc.org>

## dkimpy

   Organization: dkimpy developers/Scott Kitterman  
   Description: Python DKIM package  
   Status of Operation: Production  
   Coverage: Full spec implemented 

   * 2017-07-15: The internal test suite is incomplete, but the command line
   developmental version of validator was demonstrated to interoperate with
   the Google and AOL implementations during the interop on 2017-07-15 and the
   released version passes the tests in 
   [arc\_test\_suite](https://github.com/Valimail/arc_test_suite) with both python and python3.
   * 2018-10: Re-validated in the interop

   Licensing: Open/Other (same as dkimpy package = BCD version 2)  
   Contact Info: https://launchpad.net/dkimpy

## OpenARC

  Organization: TDP/Murray Kucherawy  
  Description: Implementation of milter functionality related to the OpenDKIM
    and OpenDMARC packages  
  Status of Operation: Beta  
  Coverage: Full implementation
  Licensing: Open/Other (same as OpenDKIM and OpenDMARC packages)  
  Implementation Notes:

  * 2018-10: Validated with one bug discovered during interop
  * 2018-11: Known issues have been resolved with release 1.0.0-Beta2

  Contact Info: <arc-discuss@dmarc.org>, <openarc-users@openarc.org>

## Mailman 3.x patch

  Organization: Mailman development team  
  Description: Integrated ARC capabilities within the Mailman 3.2 package  
  Status of Operation: Patch submitted  
  Coverage: Based on OpenARC  
  Licensing: Same as mailman package - GPL  
  Implementation Notes:

  * Appears to work properly in at least one beta deployment, but
  waiting on acceptance of the pull request into the mainline of
  mailman development
  * Discussions continuing with Mailman team to get this integrated

  Contact Info: https://www.gnu.org/software/mailman/contact.html

## Copernica/MailerQ web-based validation

  Organization: Copernica  
  Description: Web-based validation of ARC-signed messages  
  Status of Operation: Beta  
  Coverage: Full implementation
  Licensing: On-line usage only  
  Implementation Notes:

  * Released 2016-10-24
  * Requires full message content to be pasted into a web form found at
http://arc.mailerq.com/ (warning - https is not supported).
   * An additional instance of an ARC signature can be added if one is
willing to paste a private key into an unsecured web form.
   * 2017-07-15: Testing shows that results match the other implementations
listed in this section.
   * 2018-10: not tested during interop

  Contact Info: https://www.copernica.com/

## Rspamd

  Organization: Rspamd community  
  Description: ARC signing and verification module  
  Status of Operation: Production, though deployment usage is unknown  
  Coverage: Full implementation
  Licensing: Open source  
  Implementation Notes:

  * 2017-06-12: Released with version 1.6.0
  * 2017-07-15: Testing during the interop showed that the validation functionality
  interoperated with the Google, AOL, dkimpy and MailerQ implementations
  * 2018-10: Re-validated during the interop

  Contact Info: https://rspamd.com/doc/modules/arc.html and https://github.com/vstakhov/rspamd

## PERL MAIL::DKIM module

  Organization: FastMail  
  Description: Email domain authentication (sign and/or verify) module, 
previously included SPF / DKIM / DMARC, now has ARC added  
  Status of Operation: Production, deployment usage unknown  
  Coverage: Full implementation
  Licensing: Open Source  
  Implementation Notes:

  * 2017-12-15: v0.50 released with full test set passing for ARC
  * 2018-10: Revalidated during the interop and used for the creation of the
  Appendix B example

  Contact Info: http://search.cpan.org/~mbradshaw/Mail-DKIM-0.50/

## PERL Mail::Milter::Authentication module

  Organization: FastMail  
  Description: Email domain authentication milter, uses MAIL::DKIM (see above)  
  Status of Operation: Initial validation completed during IETF99 hackathon with some follow-on work 
  during the week  
  Coverage: Full implementation
  Licensing: Open Source  
  Implementation Notes:

  * 2017-07-15: Validation functionality which interoperates with Gmail, AOL, dkimpy was demonstrated; later in
  the week of IETF99, the signing functionality was reported to be working
  * 2017-07-20: ARC functionality has not yet been pushed back to the github repo but should be showing up soon
  * 2018-10: Revalidated during the interop

  Contact Info: https://github.com/fastmail/authentication_milter

## Sympa List Manager

  Organization: Sympa Dev Community  
  Description: Beta released  
  Status of Operation: Beta released  
  Coverage: Full implementation, based on Mail::DKIM module  
  Licensing: open source  
  Implementation Notes:

  * 2018-01-05: Tracked as https://github.com/sympa-community/sympa/issues/153
  * 2018-12-08: Sympa 6.2.37 beta 3 incorporates ARC support, scheduled for stable release 6.2.38 on 2018-12-21

  Contact Info: https://github.com/sympa-community

## Oracle Messaging Server

  Organization: Oracle  
  Description:  
  Status of Operation: Initial development work during IETF99 hackathon. Framework code is complete,
    crypto functionality requires integration with libsodium  
  Coverage: Work in progress  
  Licensing: Unknown  
  Implementation Notes:

  * 2018-03: Protocol handling components are completed, but crypto is not yet functional.

  Contact Info: Chris Newman, Oracle

## MessageSystems Momentum and PowerMTA platforms

  Organization: MessageSystems/SparkPost  
  Description: OpenARC integration into the LUA-enabled Momentum processing space  
  Status of Operation: Beta  
  Coverage: Same as OpenARC  
  Licensing: Unknown  
  Implementation Notes:

  * 2018-10: Beta version in private evaluation, not tested during interop.

  Contact Info: TBD
  <!-- TBD: check w/ Juan & Elliott regarding listing them here -->

## Exim

  Organization: Exim developers  
  Status of Operation: Operational; requires specific enabling for compile.  
  Coverage: Full spec implemented 
  Licensing: GPL  
  Contact Info: exim-users@exim.org  
  Implementation notes:

  * Implemented as of Exim 4.91

## Halon MTA

  Organization: Halon  
  Status of Operation: Operational as of May 2018  
  Coverage: Full spec implemented 
  Licensing: Commercial, trial version available for download  
  Contact Info: https://halon.io  
  Implementation notes:

  * GPL'd library with ARC capabilities: https://github.com/halon/libdkimpp
  * 2018-10: Validated during interop

## IIJ

  Organization: Internet Initiative Japan (IIJ) 
  Status of Operation: Operational as of October 2018  
  Coverage: Full spec implemented 
  Licensing: Internal  
  Contact Info: https://www.iij.ad.jp/en/  
  Implementation notes:

  * 2018-10: Internal MTA implementation validated during the ARC interop 

