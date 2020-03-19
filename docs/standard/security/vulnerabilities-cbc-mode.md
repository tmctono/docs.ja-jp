---
title: CBC 復号化の脆弱性
description: パディングを使用した暗号ブロックチェーン (CBC) モード対称復号化を使用してタイミングの脆弱性を検出し、軽減する方法を説明します。
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186094"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="da39b-103">パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性</span><span class="sxs-lookup"><span data-stu-id="da39b-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="da39b-104">マイクロソフトは、検証可能なパディングが適用された場合、暗号化テキストの整合性を最初に確保せずに、対称暗号化の暗号ブロックチェーン (CBC) モードで暗号化されたデータを復号化することはもはや安全ではないと考えています。状況。</span><span class="sxs-lookup"><span data-stu-id="da39b-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="da39b-105">この判断は、現在知られている暗号研究に基づいています。</span><span class="sxs-lookup"><span data-stu-id="da39b-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="da39b-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="da39b-106">Introduction</span></span>

<span data-ttu-id="da39b-107">パディング Oracle 攻撃は、暗号化されたデータに対する攻撃の一種であり、攻撃者はキーを知らなくてもデータの内容を解読できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="da39b-108">オラクルとは、実行しているアクションが正しいかどうかに関する情報を攻撃者に提供する「tell」を指します。</span><span class="sxs-lookup"><span data-stu-id="da39b-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="da39b-109">子供と一緒にボードやカードゲームをプレイ想像してみてください。</span><span class="sxs-lookup"><span data-stu-id="da39b-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="da39b-110">彼らが良い動きをしようとしていると思うので、彼らの顔が満面の笑みで点灯するとき、それはオラクルです。</span><span class="sxs-lookup"><span data-stu-id="da39b-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="da39b-111">対戦相手として、このオラクルを使用して次の動きを適切に計画することができます。</span><span class="sxs-lookup"><span data-stu-id="da39b-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="da39b-112">パディングは特定の暗号用語です。</span><span class="sxs-lookup"><span data-stu-id="da39b-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="da39b-113">データの暗号化に使用されるアルゴリズムである暗号の中には、各ブロックが固定サイズのデータブロックで機能するものもあります。</span><span class="sxs-lookup"><span data-stu-id="da39b-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="da39b-114">暗号化するデータがブロックを埋めるのに適切なサイズでない場合、データは埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="da39b-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="da39b-115">多くの形式のパディングでは、元の入力が適切なサイズであった場合でも、常に埋め込みが必要です。</span><span class="sxs-lookup"><span data-stu-id="da39b-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="da39b-116">これにより、暗号化解除時にパディングを常に安全に削除できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="da39b-117">2 つの事項を組み合わせると、Oracle を埋め込むソフトウェア実装によって、暗号化解除されたデータに有効なパディングがあるかどうかが明らかになります。</span><span class="sxs-lookup"><span data-stu-id="da39b-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="da39b-118">oracle は、「無効な埋め込み」と言う値を返す単純なものや、無効なブロックではなく、有効なブロックを処理するのに、測定可能な異なる時間を取るような複雑な何かである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="da39b-119">ブロックベースの暗号には、モードと呼ばれる別のプロパティがあり、最初のブロックのデータと 2 番目のブロックのデータとの関係が決定されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="da39b-120">最も一般的に使用されるモードの 1 つは CBC です。</span><span class="sxs-lookup"><span data-stu-id="da39b-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="da39b-121">CBC は初期化ベクトル (IV) と呼ばれる初期のランダム ブロックを導入し、前のブロックと静的暗号化の結果を組み合わせて、同じキーで同じメッセージを暗号化しても必ずしも同じ暗号化出力が生成されないようになっています。</span><span class="sxs-lookup"><span data-stu-id="da39b-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="da39b-122">攻撃者は、パディング オラクルと CBC データの構造を組み合わせて使用して、わずかに変更されたメッセージを Oracle を公開するコードに送信し、Oracle からデータが正しいことを伝えるまでデータを送信し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="da39b-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="da39b-123">この応答から、攻撃者はメッセージバイトをバイト単位で解読できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="da39b-124">最近のコンピュータ ネットワークは、攻撃者がリモート システムでの実行時間の差を非常に小さく (0.1 ミリ秒未満) 検出できるような高品質のネットワークです。</span><span class="sxs-lookup"><span data-stu-id="da39b-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="da39b-125">データが改ざんされていない場合にのみ、正常な復号化が発生すると想定されているアプリケーションは、復号化の成功と失敗の違いを観察するように設計されたツールからの攻撃に対して脆弱である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="da39b-126">このタイミングの違いは、他の言語やライブラリよりも重要な場合もありますが、アプリケーションの障害への対応を考慮すると、すべての言語とライブラリにとって、これは実用的な脅威であると考えられています。</span><span class="sxs-lookup"><span data-stu-id="da39b-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="da39b-127">この攻撃は、暗号化されたデータを変更し、Oracle で結果をテストする機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="da39b-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="da39b-128">攻撃を完全に軽減する唯一の方法は、暗号化されたデータに対する変更を検出し、そのデータに対する操作の実行を拒否することです。</span><span class="sxs-lookup"><span data-stu-id="da39b-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="da39b-129">これを行う標準的な方法は、データの署名を作成し、操作が実行される前にその署名を検証することです。</span><span class="sxs-lookup"><span data-stu-id="da39b-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="da39b-130">署名は検証可能でなければならず、攻撃者が作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="da39b-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="da39b-131">適切な署名の一般的な種類の 1 つは、キー付きハッシュ メッセージ認証コード (HMAC) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="da39b-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="da39b-132">HMAC は、HMAC を作成するユーザーと検証するユーザーにのみ知られている秘密キーを受け取るという点で、チェックサムとは異なります。</span><span class="sxs-lookup"><span data-stu-id="da39b-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="da39b-133">キーを所有していない場合、正しい HMAC を生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="da39b-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="da39b-134">データを受信したら、暗号化されたデータを取得し、自分と送信者の共有を使用して HMAC を個別に計算し、送信した HMAC を計算したデータと比較します。</span><span class="sxs-lookup"><span data-stu-id="da39b-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="da39b-135">この比較は一定の時間である必要があり、それ以外の場合は別の検出可能な oracle を追加して、別の種類の攻撃を許可します。</span><span class="sxs-lookup"><span data-stu-id="da39b-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="da39b-136">要約すると、埋め込まれた CBC ブロック暗号を安全に使用するには、データの復号化を試みる前に、一定の時間比較を使用して検証する HMAC (または別のデータ整合性チェック) と組み合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="da39b-137">変更されたすべてのメッセージは応答を生成するのに同じ時間がかかるため、攻撃は防止されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="da39b-138">脆弱なユーザー</span><span class="sxs-lookup"><span data-stu-id="da39b-138">Who is vulnerable</span></span>

<span data-ttu-id="da39b-139">この脆弱性は、独自の暗号化と復号化を実行しているマネージ アプリケーションとネイティブ アプリケーションの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="da39b-140">これには、たとえば次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="da39b-140">This includes, for example:</span></span>

- <span data-ttu-id="da39b-141">サーバーで後で復号化するために Cookie を暗号化するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="da39b-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="da39b-142">後で列を復号化するテーブルにデータを挿入する機能をユーザーに提供するデータベース アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="da39b-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="da39b-143">転送中のデータを保護するために共有キーを使用した暗号化に依存するデータ転送アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="da39b-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="da39b-144">TLS トンネル内でメッセージを暗号化および復号化するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="da39b-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="da39b-145">TLS を単独で使用しても、これらのシナリオでは保護されない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="da39b-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="da39b-146">脆弱なアプリケーション:</span><span class="sxs-lookup"><span data-stu-id="da39b-146">A vulnerable application:</span></span>

- <span data-ttu-id="da39b-147">PKCS#7 や ANSI X.923 などの検証可能なパディング モードを使用して、CBC 暗号モードを使用してデータを復号化します。</span><span class="sxs-lookup"><span data-stu-id="da39b-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="da39b-148">(MAC または非対称デジタル署名を介して) データ整合性チェックを実行せずに、復号化を実行します。</span><span class="sxs-lookup"><span data-stu-id="da39b-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="da39b-149">これは、暗号化メッセージ構文 (PKCS#7/CMS) EnvelopedData 構造体など、これらのプリミティブの上に抽象化の上に構築されたアプリケーションにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="da39b-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="da39b-150">関連する懸念事項</span><span class="sxs-lookup"><span data-stu-id="da39b-150">Related areas of concern</span></span>

<span data-ttu-id="da39b-151">調査により、マイクロソフトは、メッセージが既知または予測可能なフッター構造を持つ場合に、ISO 10126 相当のパディングで埋め込まれた CBC メッセージについてさらに懸念を抱いています。</span><span class="sxs-lookup"><span data-stu-id="da39b-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="da39b-152">たとえば、W3C XML 暗号化の構文と処理の推奨事項 (xmlenc、EncryptedXml) の規則に従って作成されたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="da39b-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="da39b-153">メッセージに署名するための W3C ガイダンスでは、暗号化が適切であると考えられていたが、マイクロソフトでは、常に暗号化してから署名を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da39b-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="da39b-154">アプリケーション開発者は、非対称キーと任意のメッセージの間に固有の信頼関係がないため、非対称署名キーの適用性を常に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="da39b-155">詳細</span><span class="sxs-lookup"><span data-stu-id="da39b-155">Details</span></span>

<span data-ttu-id="da39b-156">従来、HMAC や RSA 署名などの手段を使用して、重要なデータの暗号化と認証の両方が重要であるというコンセンサスがありました。</span><span class="sxs-lookup"><span data-stu-id="da39b-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="da39b-157">ただし、暗号化と認証操作の順序付け方法に関する明確なガイダンスは少なくてすんでいます。</span><span class="sxs-lookup"><span data-stu-id="da39b-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="da39b-158">この資料で詳しく説明している脆弱性のため、マイクロソフトのガイダンスでは、常に "暗号化して署名する" パラダイムを使用します。</span><span class="sxs-lookup"><span data-stu-id="da39b-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="da39b-159">つまり、最初に対称キーを使用してデータを暗号化し、次に暗号文(暗号化されたデータ)上で MAC または非対称署名を計算します。</span><span class="sxs-lookup"><span data-stu-id="da39b-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="da39b-160">データを復号化する場合は、逆の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="da39b-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="da39b-161">まず、暗号文の MAC または署名を確認してから、暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="da39b-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="da39b-162">「パディングオラクル攻撃」と呼ばれる脆弱性のクラスは、10年以上前から存在することが知られています。</span><span class="sxs-lookup"><span data-stu-id="da39b-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="da39b-163">これらの脆弱性により、攻撃者は、AES や 3DES などの対称ブロック アルゴリズムで暗号化されたデータを、データ ブロックあたり 4096 回を超える試行を使用して復号化できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="da39b-164">これらの脆弱性は、ブロック暗号が最も頻繁に使用され、最後にデータをパディングする検証が可能であるという事実を利用します。</span><span class="sxs-lookup"><span data-stu-id="da39b-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="da39b-165">攻撃者が暗号化テキストを改ざんし、改ざんによって最後のパディングの形式でエラーが発生したかどうかを突き出した場合、攻撃者はデータを解読できることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="da39b-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="da39b-166">最初は、パディングが有効かどうかに基づいて異なるエラー コードを返すサービスに基づいて攻撃ASP.NET攻撃を受[けた MS10-070](/security-updates/SecurityBulletins/2010/ms10-070)。</span><span class="sxs-lookup"><span data-stu-id="da39b-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="da39b-167">しかし、マイクロソフトは現在、有効なパディングと無効なパディングのタイミングの違いだけを使用して同様の攻撃を行うことを現実的であると考えています。</span><span class="sxs-lookup"><span data-stu-id="da39b-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="da39b-168">暗号化スキームが署名を採用し、(内容に関係なく) 所定の長さのデータの固定ランタイムで署名検証が実行されることを知って、データの整合性は[、サイドチャネル](https://en.wikipedia.org/wiki/Side-channel_attack)を介して攻撃者に情報を送信することなく検証することができます。</span><span class="sxs-lookup"><span data-stu-id="da39b-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="da39b-169">整合性チェックは改ざんされたメッセージを拒否するため、パディング Oracle の脅威は軽減されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="da39b-170">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="da39b-170">Guidance</span></span>

<span data-ttu-id="da39b-171">まず第一に、機密性を持つデータは、セキュア ソケット レイヤ (SSL) の後継であるトランスポート層セキュリティ (TLS) を介して送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="da39b-172">次に、アプリケーションを分析して次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="da39b-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="da39b-173">実行している暗号化と、使用しているプラットフォームと API によって提供される暗号化を正確に把握します。</span><span class="sxs-lookup"><span data-stu-id="da39b-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="da39b-174">CBC モードでの AES や 3DES などの対称[ブロック暗号アルゴリズム](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)の各層での各使用法には、秘密鍵によるデータ整合性チェック (非対称署名、HMAC、または認証済み暗号化モードを GCM や CCM などの[認証済み暗号化](https://en.wikipedia.org/wiki/Authenticated_encryption)(AE) モードに変更する) が組み込まれているかどうか確認してください。</span><span class="sxs-lookup"><span data-stu-id="da39b-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="da39b-175">現在の調査によると、認証と暗号化の手順が非AE暗号化モードに対して独立して実行される場合、暗号文(暗号化してから署名)を認証することが最良の一般的な選択肢であると一般的に考えられています。</span><span class="sxs-lookup"><span data-stu-id="da39b-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="da39b-176">しかし、暗号化に対する万能の正解はなく、この一般化はプロの暗号学者からの指示されたアドバイスほど良くありません。</span><span class="sxs-lookup"><span data-stu-id="da39b-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="da39b-177">メッセージング形式を変更できないが、認証されていない CBC 復号化を実行するアプリケーションは、次のような緩和策を組み込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da39b-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="da39b-178">復号化を許可せずに復号化し、パディングを検証または削除する:</span><span class="sxs-lookup"><span data-stu-id="da39b-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="da39b-179">適用されたパディングは、アプリケーションに負担を移す必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="da39b-180">利点は、パディングの検証と削除を他のアプリケーション データ検証ロジックに組み込むことができるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="da39b-181">パディング検証とデータ検証が一定時間で行える場合、脅威は減少します。</span><span class="sxs-lookup"><span data-stu-id="da39b-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="da39b-182">パディングの解釈は、知覚されるメッセージの長さを変更するので、このアプローチから発されるタイミング情報がまだあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="da39b-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="da39b-183">復号化パディング モードを ISO10126 に変更します。</span><span class="sxs-lookup"><span data-stu-id="da39b-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="da39b-184">ISO10126 復号化パディングは、PKCS7 暗号化パディングと ANSIX923 暗号化パディングの両方と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="da39b-185">モードを変更すると、パディング・オラクルの知識がブロック全体ではなく 1 バイトに減ります。</span><span class="sxs-lookup"><span data-stu-id="da39b-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="da39b-186">ただし、コンテンツに XML 要素の終了など、既知のフッターがある場合、関連する攻撃は引き続きメッセージの残りの部分を攻撃できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="da39b-187">また、攻撃者が同じプレーンテキストを異なるメッセージ オフセットで複数回暗号化する可能性がある場合でも、プレーンテキストの回復を防止することはできません。</span><span class="sxs-lookup"><span data-stu-id="da39b-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="da39b-188">タイミング信号を減衰させるために復号化コールの評価をゲートします。</span><span class="sxs-lookup"><span data-stu-id="da39b-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="da39b-189">ホールド時間の計算は、埋め込みを含むデータ セグメントに対して、復号化操作が必要とする最大時間を超える最小時間を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="da39b-190">時間の計算は[、(](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)ロールオーバー/オーバーフローの対象となる)または2つのシステムタイムスタンプ(NTP調整エラー<xref:System.Environment.TickCount?displayProperty=nameWithType>の影響を受ける)を使用してではなく、高解像度タイムスタンプの取得のガイダンスに従って行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="da39b-191">時間計算には、マネージ アプリケーションまたは C++ アプリケーションで発生する可能性のあるすべての例外を含む、最後に埋め込まれたもの以外に、復号化操作を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="da39b-192">成功または失敗がまだ決定されている場合、タイミング ゲートは、期限が切れたときに失敗を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="da39b-193">認証されていない復号化を実行しているサービスでは、"無効な" メッセージが大量に送信されたことを検出するために監視を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="da39b-194">このシグナルは、誤検知(正当に破損したデータ)と偽陰性(検出を回避するために十分に長い時間にわたって攻撃を広げる)の両方を運ぶことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="da39b-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="da39b-195">脆弱なコードを見つける - ネイティブ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="da39b-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="da39b-196">Windows 暗号化: 次世代 (CNG) ライブラリに対してビルドされたプログラムの場合:</span><span class="sxs-lookup"><span data-stu-id="da39b-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="da39b-197">復号化の呼び出しは、フラグを指定する[BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)に対する呼び出しです`BCRYPT_BLOCK_PADDING`。</span><span class="sxs-lookup"><span data-stu-id="da39b-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="da39b-198">キー ハンドルは[、BCryptSetProperty を](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty)呼び出して初期化`BCRYPT_CHAIN_MODE_CBC`[BCRYPT_CHAINING_MODE。](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE)</span><span class="sxs-lookup"><span data-stu-id="da39b-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="da39b-199">既定`BCRYPT_CHAIN_MODE_CBC`では、影響を受けるコードに 対`BCRYPT_CHAINING_MODE`して値が割り当てられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="da39b-200">古い Windows 暗号化 API に対してビルドされたプログラムの場合:</span><span class="sxs-lookup"><span data-stu-id="da39b-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="da39b-201">復号化の呼び出しは[、CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt)とを使用します`Final=TRUE`。</span><span class="sxs-lookup"><span data-stu-id="da39b-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="da39b-202">キー ハンドルは`CRYPT_MODE_CBC`[、cryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam)を呼び出して初期化[KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam)に設定されています。</span><span class="sxs-lookup"><span data-stu-id="da39b-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="da39b-203">既定`CRYPT_MODE_CBC`では、影響を受けるコードに 対`KP_MODE`して値が割り当てられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="da39b-204">脆弱なコードを検出する - マネージ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="da39b-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="da39b-205">復号化の呼び出しは、 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])>または<xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>のメソッドに対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="da39b-206">これには、.NET 内の次の派生型が含まれますが、サードパーティの型も含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="da39b-207">プロパティ<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>は、 、 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>、または<xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>に設定されています。</span><span class="sxs-lookup"><span data-stu-id="da39b-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="da39b-208">デフォルト<xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>であるため、影響を受けるコードがプロパティを<xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>割り当てなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="da39b-209">プロパティ<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>は次の値に設定されました。<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="da39b-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="da39b-210">デフォルト<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>であるため、影響を受けるコードがプロパティを<xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>割り当てなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="da39b-211">脆弱なコードを見つける - 暗号メッセージの構文</span><span class="sxs-lookup"><span data-stu-id="da39b-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="da39b-212">暗号化されたコンテンツが AES の CBC モードを使用する認証されていない CMS EnvelopedData メッセージ (2.16.840.1.101.3.4.1.2,2.16.840.1.101.3.4.1.22、 2.16.840.1.101.3.4.4.42、DES (1.3.14.3.2.7)、3DES (1.2.840.113549.3.7)またはRC2 (1.2.840.113549.3.2)また、CBC モードで他のブロック暗号アルゴリズムを使用するメッセージも含まれます。</span><span class="sxs-lookup"><span data-stu-id="da39b-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="da39b-213">ストリーム暗号はこの特定の脆弱性の影響を受けにくいですが、マイクロソフトでは ContentEncryptionAlgorithm 値の検査を行う際に常にデータを認証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da39b-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="da39b-214">マネージ アプリケーションの場合、CMS EnvelopedData BLOB は、 に<xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>渡される任意の値として検出できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="da39b-215">ネイティブ アプリケーションの場合、CMS EnvelopedData BLOB は、結果として[得られるCMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam)`CMSG_ENVELOPED`が CryptMsgControl を介して命令を送信される[CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) `CMSG_CTRL_DECRYPT`を介[CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)して CMS ハンドルに提供される任意の値として検出できます。</span><span class="sxs-lookup"><span data-stu-id="da39b-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="da39b-216">脆弱なコード例 - マネージ</span><span class="sxs-lookup"><span data-stu-id="da39b-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="da39b-217">このメソッドは、Cookie を読み取って復号化しますが、データ整合性チェックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="da39b-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="da39b-218">したがって、このメソッドによって読み取られる Cookie の内容は、その Cookie を受け取ったユーザー、または暗号化された Cookie 値を取得した攻撃者によって攻撃される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="da39b-219">推奨されるプラクティスに従ったコード例 - マネージド</span><span class="sxs-lookup"><span data-stu-id="da39b-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="da39b-220">次のサンプル コードでは、標準以外のメッセージ形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="da39b-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="da39b-221">ここで、`cipher_algorithm_id`および`hmac_algorithm_id`アルゴリズム識別子は、それらのアルゴリズムのアプリケーションローカル (非標準) 表現です。</span><span class="sxs-lookup"><span data-stu-id="da39b-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="da39b-222">これらの識別子は、既存のメッセージング プロトコルの他の部分では、専用の連結バイト ストリームとしてではなく意味を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="da39b-223">また、この例では、暗号化キーと HMAC キーの両方を派生させるために、単一のマスター キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="da39b-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="da39b-224">これは、1 つのキーを使用したアプリケーションをデュアルキーアプリケーションに変換する場合と、2 つのキーを異なる値として保持することを推奨する利便性の両方として提供されます。</span><span class="sxs-lookup"><span data-stu-id="da39b-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="da39b-225">さらに、HMAC キーと暗号化キーが同期から外れることができないことを保証します。</span><span class="sxs-lookup"><span data-stu-id="da39b-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="da39b-226">このサンプルでは、暗号化または復号化<xref:System.IO.Stream>のどちらも受け入れません。</span><span class="sxs-lookup"><span data-stu-id="da39b-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="da39b-227">現在のデータ形式では、値が暗号化テキストの前`hmac_tag`にあるため、1 回の暗号化が困難になります。</span><span class="sxs-lookup"><span data-stu-id="da39b-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="da39b-228">ただし、この形式は、パーサーをシンプルにするために、固定サイズの要素をすべて最初に保持するため選択されました。</span><span class="sxs-lookup"><span data-stu-id="da39b-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="da39b-229">このデータ形式では、1 パス復号化が可能ですが、実装者は GetHashAndReset を呼び出し、TransformFinalBlock を呼び出す前に結果を検証するように注意してください。</span><span class="sxs-lookup"><span data-stu-id="da39b-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="da39b-230">ストリーミング暗号化が重要な場合は、別の AE モードが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da39b-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
