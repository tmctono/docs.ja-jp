---
title: パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性
description: 検出および暗号ブロック チェーン (CBC) モードでパディングを使用して暗号化解除の対称のタイミングの脆弱性を軽減する方法について説明します。
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d8c2593cdbc4bbff2b1507196989282b16aa9a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933901"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="9b765-103">パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性</span><span class="sxs-lookup"><span data-stu-id="9b765-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="9b765-104">Microsoft は、安全を除き、暗号化テキストの整合性を確認せずに検証可能な埋め込みが適用されているときに、対称暗号化の暗号ブロック チェーン (CBC) モードで暗号化されたデータを復号化には不要になったと考えています非常に限定。状況。</span><span class="sxs-lookup"><span data-stu-id="9b765-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="9b765-105">この判断は、現在認識されている暗号リサーチに基づいています。</span><span class="sxs-lookup"><span data-stu-id="9b765-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="9b765-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="9b765-106">Introduction</span></span>

<span data-ttu-id="9b765-107">埋め込みの oracle 攻撃とは、攻撃者がキーを知ることがなく、データの内容を復号化には、暗号化されたデータに対する攻撃の一種です。</span><span class="sxs-lookup"><span data-stu-id="9b765-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="9b765-108">Oracle は参照を"なのかを"は、実行しているアクションが正しいかどうかについて、攻撃者の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b765-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="9b765-109">ボードの再生を想像してくださいまたは子カード ゲームです。</span><span class="sxs-lookup"><span data-stu-id="9b765-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="9b765-110">ときに当惑顔点灯笑顔で彼女は彼女と思われるため、oracle である、適切な移動を行うためについて。</span><span class="sxs-lookup"><span data-stu-id="9b765-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="9b765-111">、、対戦相手として使用できますこの oracle、次の操作を適切に計画します。</span><span class="sxs-lookup"><span data-stu-id="9b765-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="9b765-112">余白は、特定の暗号用語です。</span><span class="sxs-lookup"><span data-stu-id="9b765-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="9b765-113">データの暗号化に使用するアルゴリズムであり、一部の暗号は、各ブロックが固定サイズのデータのブロックで動作します。</span><span class="sxs-lookup"><span data-stu-id="9b765-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="9b765-114">暗号化するデータが、要素を入力する適切なサイズでない場合はこれまでに、データが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="9b765-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="9b765-115">埋め込みの多くの形式では、常に存在する場合でも、元の入力が適切なサイズがその埋め込みが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b765-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="9b765-116">これにより、余白を常に暗号化解除時に削除しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="9b765-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="9b765-117">次の 2 つをまとめて、パディングの oracle ソフトウェアの実装は復号化されたデータに有効な余白があるかどうかがわかります。</span><span class="sxs-lookup"><span data-stu-id="9b765-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="9b765-118">Oracle は、「無効な埋め込み」ことを示す値を返すように単純なものか、無効なブロックではなく有効なブロックを処理するさまざまなある程度までの時間がかかってのような複雑なものになります。</span><span class="sxs-lookup"><span data-stu-id="9b765-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="9b765-119">ブロック ベースの暗号化には 2 番目のブロック内のデータに最初のブロック内のデータのリレーションシップを決定すると、モードと呼ばれる、別のプロパティがあり、具合です。</span><span class="sxs-lookup"><span data-stu-id="9b765-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="9b765-120">CBC は、最もよく使用されるモードのいずれか。</span><span class="sxs-lookup"><span data-stu-id="9b765-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="9b765-121">CBC は、既知のとして初期化ベクター (IV)、初期乱数ブロックを紹介し、同じ暗号化された出力を常に生成しない同じキーを持つ、同じメッセージを暗号化するように静的な暗号化の結果と、前のブロックを結合します。</span><span class="sxs-lookup"><span data-stu-id="9b765-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="9b765-122">Oracle を公開するコードにわずかに変更されたメッセージを送信し、oracle では、ことを示すまでデータの送信を保持するデータが正しく、攻撃者は CBC データ構造と組み合わせて、パディングの oracle を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b765-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="9b765-123">この応答から、攻撃者は、バイトごとのメッセージを暗号化解除できます。</span><span class="sxs-lookup"><span data-stu-id="9b765-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="9b765-124">最近のコンピューターのネットワークはこのような高品質の攻撃者がリモート システム上 (0.1 ミリ秒未満) の実行の相違点の時間が非常に小さい検出できます。</span><span class="sxs-lookup"><span data-stu-id="9b765-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="9b765-125"> 成功と失敗の復号化の違いを観察するように設計されたツールからの攻撃に対して脆弱になりますが、データが改ざんされた場合にのみを正常に復号化が発生すると仮定すると、アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="9b765-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="9b765-126">このタイミングの違いは、他よりも、いくつかの言語またはライブラリでより重要なことがありますが、障害に対するアプリケーションの応答がアカウントに実行したときに、すべての言語とライブラリの実際的な脅威はこれを今すぐ信じします。</span><span class="sxs-lookup"><span data-stu-id="9b765-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="9b765-127">この攻撃は、暗号化されたデータを変更し、oracle と結果をテストする機能に依存しています。</span><span class="sxs-lookup"><span data-stu-id="9b765-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="9b765-128">暗号化されたデータへの変更を検出し、それに対するアクションは実行を拒否するのには完全に攻撃を軽減するしかありません。</span><span class="sxs-lookup"><span data-stu-id="9b765-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="9b765-129">これを行う標準的な方法では、データの署名を作成し、すべての操作を実行する前に、その署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="9b765-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="9b765-130">署名は検証可能である必要があります、攻撃者が作成できないは、暗号化されたデータを変更し、変更されたデータに基づいて新しい署名の計算のそれ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="9b765-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="9b765-131">適切なシグネチャの 1 つの一般的な型は、キー付きハッシュ メッセージ認証コード (HMAC) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9b765-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="9b765-132">HMAC は、既知の HMAC を生成する人にのみ、ユーザーの検証に秘密キーを受け取るというチェックサムと異なります。</span><span class="sxs-lookup"><span data-stu-id="9b765-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="9b765-133">キーを所有している、なしには、正しい HMAC を生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b765-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="9b765-134">データが表示されたら、するは暗号化されたデータを取得、個別にコンピューティングいない HMAC の秘密キーを使用し、する、送信者の共有、比較が送信されるとき、いずれかに対してする HMAC 計算。</span><span class="sxs-lookup"><span data-stu-id="9b765-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="9b765-135">この比較は一定の時間である必要があります、それ以外の場合追加した別の検出可能な oracle では、異なる種類の攻撃を許可します。</span><span class="sxs-lookup"><span data-stu-id="9b765-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="9b765-136">要約すると、使用するには、CBC ブロック暗号を安全に埋め込み、データを復号化する前に一定の時間の比較を使用して検証する、HMAC (または別のデータの整合性チェック)、それらを組み合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b765-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="9b765-137">変更されたすべてのメッセージでは、応答を生成するために同じ時間がかかる、攻撃が回避されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="9b765-138">脆弱であります。</span><span class="sxs-lookup"><span data-stu-id="9b765-138">Who is vulnerable</span></span>

<span data-ttu-id="9b765-139">この脆弱性は、独自の暗号化と復号化を実行しているアプリケーションがマネージ コードとネイティブの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="9b765-140">これが含まれている例。</span><span class="sxs-lookup"><span data-stu-id="9b765-140">This includes, for example:</span></span>

- <span data-ttu-id="9b765-141">復号化に後で、サーバー上の cookie を暗号化するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="9b765-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="9b765-142">列を持つユーザーがテーブルにデータを挿入する機能を提供するデータベース アプリケーションは、後で復号化します。</span><span class="sxs-lookup"><span data-stu-id="9b765-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="9b765-143">データは、共有キーを使用して、転送中のデータを保護する暗号化に依存するアプリケーションを転送します。</span><span class="sxs-lookup"><span data-stu-id="9b765-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="9b765-144">暗号化し、「内」TLS トンネルのメッセージを復号化するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="9b765-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="9b765-145">だけで TLS を使用してが保護されないこれらのシナリオで注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b765-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="9b765-146">脆弱なアプリケーションの場合:</span><span class="sxs-lookup"><span data-stu-id="9b765-146">A vulnerable application:</span></span>

- <span data-ttu-id="9b765-147">CBC 暗号モードを PKCS #7 または ANSI X.923 など、検証可能なパディング モードを使用してデータを復号化します。</span><span class="sxs-lookup"><span data-stu-id="9b765-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="9b765-148">(MAC または非対称のデジタル署名) を使って、データの整合性チェックを実行せず、復号化を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b765-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="9b765-149">これは、Cryptographic Message Syntax (PKCS #7/CMS) EnvelopedData 構造など、これらのプリミティブの上に抽象化の上に構築されたアプリケーションにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="9b765-150">関連する重要な領域</span><span class="sxs-lookup"><span data-stu-id="9b765-150">Related areas of concern</span></span>

<span data-ttu-id="9b765-151">Research は ISO 10126 等価では、メッセージのよく知られているか、予測可能なフッター構造内のスペースで埋められます CBC メッセージについてさらに関係する Microsoft の led が。</span><span class="sxs-lookup"><span data-stu-id="9b765-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="9b765-152">たとえば、W3C XML Encryption Syntax と処理の推奨事項 (xmlenc encryptedxml の互換性) の規則の下で準備のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="9b765-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="9b765-153">メッセージに署名し、暗号化するには、W3C ガイダンスと見なされていました適切な時点で、中に、Microsoft は常に暗号化、署名を行うようになりました推奨します。</span><span class="sxs-lookup"><span data-stu-id="9b765-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="9b765-154">アプリケーション開発者は常に、非対称署名キーの適用性の確認に注意してください、非対称キーと任意のメッセージの本質的な信頼関係が存在しないためです。</span><span class="sxs-lookup"><span data-stu-id="9b765-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="9b765-155">説明</span><span class="sxs-lookup"><span data-stu-id="9b765-155">Details</span></span>

<span data-ttu-id="9b765-156">従来は、両方の暗号化および HMAC または RSA 署名などの手段を使用して、重要なデータを認証することが重要合意がありました。</span><span class="sxs-lookup"><span data-stu-id="9b765-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="9b765-157">ただし、暗号化および認証操作をシーケンス処理する方法について明確なガイダンスは少ないがありました。</span><span class="sxs-lookup"><span data-stu-id="9b765-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="9b765-158">この記事に記載された脆弱性により Microsoft のガイダンスは常に「を暗号化し、サインオン」パラダイムを使用するようになりましたが。</span><span class="sxs-lookup"><span data-stu-id="9b765-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="9b765-159">最初に対称キーを使用してデータを暗号化し、MAC、または非対称署名、暗号化テキスト (暗号化されたデータ) を計算します。</span><span class="sxs-lookup"><span data-stu-id="9b765-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="9b765-160">データを復号化、逆を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b765-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="9b765-161">最初に、MAC や、暗号化テキストの署名を確認し、暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="9b765-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="9b765-162">10 年以上にわたって存在に呼ばれる「パディング oracle 攻撃」と呼ばれる脆弱性のクラスです。</span><span class="sxs-lookup"><span data-stu-id="9b765-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="9b765-163">これらの脆弱性を許可すると、攻撃者がデータのブロックあたり 4,096 個以下の試行を使用して、AES および 3 des などの対称ブロック アルゴリズムで暗号化されたデータを復号化します。</span><span class="sxs-lookup"><span data-stu-id="9b765-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="9b765-164">これらの脆弱性のため暗号をブロックするファクトの使用は、最後に検証可能な埋め込みデータを最も頻繁に使用します。</span><span class="sxs-lookup"><span data-stu-id="9b765-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="9b765-165">場合は、攻撃者は、暗号化テキストを改ざんし、末尾の余白の形式でエラーが発生改ざんが行われたかどうかを検出、攻撃者は、データを解読することができます、それが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b765-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="9b765-166">埋め込みが ASP.NET の脆弱性など、有効かどうかに基づいて別のエラー コードを返すようサービスに実用的な攻撃されたに基づいて最初に、 [MS10 070](/security-updates/SecurityBulletins/2010/ms10-070)します。</span><span class="sxs-lookup"><span data-stu-id="9b765-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="9b765-167">ただし、Microsoft ようになりましたものであるが有効および無効な余白の処理間のタイミングでは、差分のみを使用して類似の攻撃を実施するは実用的であります。</span><span class="sxs-lookup"><span data-stu-id="9b765-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="9b765-168">すべての情報を生成せず、データの整合性を確認できます暗号化スキームは、署名を使用し、(内容) に関係なくデータの指定された長さの固定のランタイムと、署名の検証が実行されること、使用して攻撃者、[側チャネル](https://en.wikipedia.org/wiki/Side-channel_attack)します。</span><span class="sxs-lookup"><span data-stu-id="9b765-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="9b765-169">整合性チェックは、改ざんされたメッセージを拒否するため、埋め込み oracle 脅威が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="9b765-170">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="9b765-170">Guidance</span></span>

<span data-ttu-id="9b765-171">何よりもまず、経由でトランスポート層セキュリティ (TLS)、Secure Sockets Layer (SSL) に後続必要がある機密性のあるすべてのデータに送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b765-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="9b765-172">次に、アプリケーションを分析します。</span><span class="sxs-lookup"><span data-stu-id="9b765-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="9b765-173">実行しているどのような暗号化とどのような暗号化は、プラットフォームと Api を使用しているによって提供されていると正確に理解します。</span><span class="sxs-lookup"><span data-stu-id="9b765-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="9b765-174">各使用法、対称の各層であることがはっきり[ブロック暗号アルゴリズム](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)AES および 3 des、CBC モードでは、シークレット キー付きのデータの整合性チェックの使用を組み込むことなど、(、非対称の署名、HMAC する暗号モードを変更します。[認証暗号化](https://en.wikipedia.org/wiki/Authenticated_encryption)(AE) モード CCM、GCM など)。</span><span class="sxs-lookup"><span data-stu-id="9b765-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="9b765-175">現在の研究に基づく、一般と思われます場合、認証と暗号化の手順は、の暗号化のない AE モード別に行う、暗号文の認証 (暗号化-、-記号) が最適な一般的なオプションです。</span><span class="sxs-lookup"><span data-stu-id="9b765-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="9b765-176">ただし、暗号化万能型の正しい答えはありません、この一般論がプロフェッショナルな暗号技術者からのアドバイスをすぐに有向はありません。</span><span class="sxs-lookup"><span data-stu-id="9b765-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="9b765-177">メッセージング形式の変更が認証されていない CBC 暗号化解除を実行できないアプリケーションなどの軽減策を組み込むしようとすることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="9b765-178">復号化、パディングを削除するを確認または復号化を許可しません。</span><span class="sxs-lookup"><span data-stu-id="9b765-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="9b765-179">適用された埋め込みは削除するか、無視する必要がある、負荷をアプリケーションに移動します。</span><span class="sxs-lookup"><span data-stu-id="9b765-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="9b765-180">利点は、その他のアプリケーション データの検証ロジックに組み込むことが、埋め込みの検証と削除です。</span><span class="sxs-lookup"><span data-stu-id="9b765-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="9b765-181">パディングの検証とデータの検証は、定数時間で完了できます、脅威が減少します。</span><span class="sxs-lookup"><span data-stu-id="9b765-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="9b765-182">埋め込みの解釈が認識されるメッセージの長さを変更するためもありますタイミングについてはこのアプローチから生成されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="9b765-183">ISO10126 を復号化のパディング モードを変更します。</span><span class="sxs-lookup"><span data-stu-id="9b765-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="9b765-184">ISO10126 復号化の埋め込みが PKCS7 暗号化パディングと ANSIX923 暗号化パディングの両方との互換性です。</span><span class="sxs-lookup"><span data-stu-id="9b765-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="9b765-185">モードを変更すると、ブロック全体ではなく、1 バイトを埋め込み oracle サポート技術情報が減少します。</span><span class="sxs-lookup"><span data-stu-id="9b765-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="9b765-186">ただし、コンテンツがある XML 要素では、終了などのよく知られているフッター場合、関連する攻撃は、メッセージの残りの部分を攻撃する続行できます。</span><span class="sxs-lookup"><span data-stu-id="9b765-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="9b765-187">これは防ぐことも、攻撃者が別のメッセージ オフセットで複数回暗号化された同じプレーン テキストを強制する状況でプレーン テキストの回復。</span><span class="sxs-lookup"><span data-stu-id="9b765-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="9b765-188">ゲートするタイミングのシグナルを緩衝復号化の呼び出しの評価:</span><span class="sxs-lookup"><span data-stu-id="9b765-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="9b765-189">ホールド時間の計算の余白を含む任意のデータ セグメントに対して暗号化解除操作が行われる最大時間を超える場合の最小値が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b765-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="9b765-190">ガイダンスに従い、時間の計算を行う必要があります[高解像度のタイムスタンプを取得](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)を使用していない<xref:System.Environment.TickCount?displayProperty=nameWithType>(対象ロール-over/オーバーフロー) または 2 つのシステムのタイムスタンプ (NTP 調整の対象を削除します。エラーの場合)。</span><span class="sxs-lookup"><span data-stu-id="9b765-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="9b765-191">時間計算する必要があります内のすべての潜在的な例外を含む、復号化操作を含む管理または末尾に埋め込まれただけでなく、C++ アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="9b765-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="9b765-192">成功または失敗をまだ決定されていますが場合、タイミング ゲートは、有効期限が切れるときにエラーを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b765-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="9b765-193">認証されていない復号化を実行しているサービスは、大量の「無効」のメッセージが取得することを検出する監視が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b765-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="9b765-194">このシグナルが (合法的に破損したデータ) の偽陽性と偽陰性の (分散化検出を回避するための十分に長い時間の経過と共に攻撃) の両方を実行するも留意してください。</span><span class="sxs-lookup"><span data-stu-id="9b765-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="9b765-195">脆弱なコードは、ネイティブ アプリケーションの検索</span><span class="sxs-lookup"><span data-stu-id="9b765-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="9b765-196">Windows の暗号化に対してビルドされたプログラム。[次へ] の Generation (CNG) ライブラリ:</span><span class="sxs-lookup"><span data-stu-id="9b765-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="9b765-197">復号化の呼び出しはに対する[BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)を指定して、`BCRYPT_BLOCK_PADDING`フラグ。</span><span class="sxs-lookup"><span data-stu-id="9b765-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="9b765-198">キー ハンドルが呼び出すことによって初期化されている[BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty)で[BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE)設定`BCRYPT_CHAIN_MODE_CBC`します。</span><span class="sxs-lookup"><span data-stu-id="9b765-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="9b765-199">`BCRYPT_CHAIN_MODE_CBC`既定値は、影響を受けるはコードに、値を割り当てることがない可能性がありますが`BCRYPT_CHAINING_MODE`します。</span><span class="sxs-lookup"><span data-stu-id="9b765-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="9b765-200">以前の Windows 暗号化 API に対してビルドされたプログラム。</span><span class="sxs-lookup"><span data-stu-id="9b765-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="9b765-201">復号化の呼び出しはに対する[CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt)で`Final=TRUE`します。</span><span class="sxs-lookup"><span data-stu-id="9b765-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="9b765-202">キー ハンドルが呼び出すことによって初期化されている[CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam)で[KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam)設定`CRYPT_MODE_CBC`します。</span><span class="sxs-lookup"><span data-stu-id="9b765-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="9b765-203">`CRYPT_MODE_CBC`既定値は、影響を受けるはコードに、値を割り当てることがない可能性がありますが`KP_MODE`します。</span><span class="sxs-lookup"><span data-stu-id="9b765-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="9b765-204">脆弱性のあるコードの検索 - マネージ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9b765-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="9b765-205">復号化の呼び出しはに対する、<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor>または<xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])>メソッド<xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="9b765-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="9b765-206">これは、.NET 内で次の派生型が含まれていますが、サード パーティの型を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9b765-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <span data-ttu-id="9b765-207"><xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>プロパティに設定されました<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>、 <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>、または<xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="9b765-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="9b765-208"><xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>既定値は、影響を受けるはコードが割り当てられませんが、<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9b765-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="9b765-209"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>プロパティに設定されました <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9b765-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="9b765-210"><xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>既定値は、影響を受けるはコードが割り当てられませんが、<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9b765-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="9b765-211">暗号化メッセージ構文脆弱性のあるコードの検索</span><span class="sxs-lookup"><span data-stu-id="9b765-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="9b765-212">暗号化されたコンテンツを持つ、CBC モードの AES (2.16.840.1.101.3.4.1.2、2.16.840.1.101.3.4.1.22、2.16.840.1.101.3.4.1.42)、DES (1.3.14.3.2.7)、3 des を使用して認証されていない、CMS EnvelopedData メッセージ (1.2.840.113549.3.7) または RC2 (1.2.840.113549.3.2) は、脆弱性もとしてメッセージ CBC モードの他のブロック暗号アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b765-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="9b765-213">ストリーム暗号は、この特定の脆弱性に影響を受けやすい中、ContentEncryptionAlgorithm 値を調べることで、常にで、データの認証を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b765-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="9b765-214">Blob は、CMS EnvelopedData、マネージ アプリケーションに渡されるすべての値が検出<xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>します。</span><span class="sxs-lookup"><span data-stu-id="9b765-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="9b765-215">ネイティブのアプリケーションを使用して CMS ハンドルを指定した値として CMS EnvelopedData blob を検出できる[CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate)が結果として[CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam)は`CMSG_ENVELOPED`CMS ハンドルや後で送信、`CMSG_CTRL_DECRYPT`命令を使用して[CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)します。</span><span class="sxs-lookup"><span data-stu-id="9b765-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="9b765-216">脆弱なコード例の管理</span><span class="sxs-lookup"><span data-stu-id="9b765-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="9b765-217">Cookie を読み取ってを復号化し、データの整合性チェックが表示されません。</span><span class="sxs-lookup"><span data-stu-id="9b765-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="9b765-218">そのため、このメソッドによって読み取られる cookie の内容は、受信したユーザーまたは暗号化された cookie の値を取得した任意の攻撃者によって攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="9b765-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="9b765-219">推奨されるベスト プラクティス - マネージ コードの次の例</span><span class="sxs-lookup"><span data-stu-id="9b765-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="9b765-220">次のサンプル コードの非標準のメッセージ形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b765-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="9b765-221">場所、`cipher_algorithm_id`と`hmac_algorithm_id`アルゴリズム識別子は、これらのアルゴリズムのアプリケーションのローカル (標準) の表現です。</span><span class="sxs-lookup"><span data-stu-id="9b765-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="9b765-222">これらの識別子は、ベア連結されたバイト ストリームとしての代わりに、既存のメッセージング プロトコルの他の部分で意味をようにできます。</span><span class="sxs-lookup"><span data-stu-id="9b765-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="9b765-223">この例では、1 つのマスター _ キーを使用して、暗号化キーと、HMAC キーの両方を派生します。</span><span class="sxs-lookup"><span data-stu-id="9b765-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="9b765-224">デュアル キー付きのアプリケーションにし、2 つのキーとして別の値を維持する方法の片方向キーとアプリケーションを有効にするため、利便性のためであると指定されます。</span><span class="sxs-lookup"><span data-stu-id="9b765-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="9b765-225">さらに、同期、HMAC キーと暗号化キーを取得できませんを保証します。</span><span class="sxs-lookup"><span data-stu-id="9b765-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="9b765-226">このサンプルは受け入れません、<xref:System.IO.Stream>暗号化または復号化します。</span><span class="sxs-lookup"><span data-stu-id="9b765-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="9b765-227">現在のデータ形式で 1 回暗号化困難なため、`hmac_tag`値の前に、暗号化テキスト。</span><span class="sxs-lookup"><span data-stu-id="9b765-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="9b765-228">ただし、この形式は、パーサーを単純に先頭にあるすべての固定サイズ要素に保持するために選択されました。</span><span class="sxs-lookup"><span data-stu-id="9b765-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="9b765-229">このデータ形式に 1 回の復号化は、実装者を GetHashAndReset を呼び出し、TransformFinalBlock を呼び出す前に結果を確認する警告が表示されますが、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b765-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="9b765-230">ストリーミングの暗号化が重要な場合は、さまざまな AE モードが必要に可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b765-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
