---
title: '方法: 一貫性を保って X.509 証明書を参照する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: 2214517784d311cbd0fe487fd6db2cbf48189955
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662785"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="a525d-102">方法: 一貫性を保って X.509 証明書を参照する</span><span class="sxs-lookup"><span data-stu-id="a525d-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="a525d-103">証明書を識別する方法には、証明書のハッシュを使用する方法、発行者とシリアル番号を使用する方法、またはサブジェクト キー識別子 (SKI) を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="a525d-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="a525d-104">SKI を使用すると、証明書のサブジェクト公開キーを一意に識別できます。SKI は、XML デジタル署名を処理する場合によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="a525d-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="a525d-105">SKI の値は、X.509 証明書形式の一部では通常、 *X.509 証明書の拡張*します。</span><span class="sxs-lookup"><span data-stu-id="a525d-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="a525d-106">Windows Communication Foundation (WCF) は、既定値を持つ*参照スタイル*SKI 拡張が証明書に見つからない場合は、発行者とシリアル番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="a525d-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="a525d-107">証明書に SKI 拡張が含まれる場合、既定の参照スタイルは SKI を使用してその証明書を識別します。</span><span class="sxs-lookup"><span data-stu-id="a525d-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="a525d-108">場合、アプリケーションの開発を途中から SKI 拡張を使用する証明書に SKI 拡張を使用しない証明書を使用して切り替えることが、WCF で生成されたメッセージで使用される参照スタイルも変更します。</span><span class="sxs-lookup"><span data-stu-id="a525d-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="a525d-109">SKI 拡張が存在するかどうかに関係なく、一貫性のある参照スタイルが必要な場合は、次のコードに示されているような参照スタイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a525d-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a525d-110">例</span><span class="sxs-lookup"><span data-stu-id="a525d-110">Example</span></span>  
 <span data-ttu-id="a525d-111">次の例では、1 つの一貫した参照スタイル (ユーザー名とシリアル番号) を使用するカスタム セキュリティ バインド要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="a525d-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a525d-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a525d-112">Compiling the Code</span></span>  
 <span data-ttu-id="a525d-113">コードのコンパイルには次の名前空間が必要です。</span><span class="sxs-lookup"><span data-stu-id="a525d-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="a525d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a525d-114">See also</span></span>

- [<span data-ttu-id="a525d-115">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="a525d-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
