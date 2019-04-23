---
title: PublicKeyBlob 構造体
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a361e04b6f8f39ec0083471d8cb47d5a29376c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214820"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="c337f-102">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="c337f-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="c337f-103">公開/秘密キーのペアの公開キーをバイナリ形式で表します。</span><span class="sxs-lookup"><span data-stu-id="c337f-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c337f-104">構文</span><span class="sxs-lookup"><span data-stu-id="c337f-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="c337f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c337f-105">Members</span></span>  
  
|<span data-ttu-id="c337f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c337f-106">Member</span></span>|<span data-ttu-id="c337f-107">説明</span><span class="sxs-lookup"><span data-stu-id="c337f-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="c337f-108">署名アルゴリズムの識別子 (型の`ALG_ID`WinCrypt.h で定義されている、) の公開キー。</span><span class="sxs-lookup"><span data-stu-id="c337f-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="c337f-109">ハッシュ アルゴリズムの識別子 (型の`ALG_ID`WinCrypt.h で定義されている、) の公開キー。</span><span class="sxs-lookup"><span data-stu-id="c337f-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="c337f-110">(バイト単位)、キーの長さ。</span><span class="sxs-lookup"><span data-stu-id="c337f-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="c337f-111">CryptoAPI によって返される形式でキーの値を含む可変長バイト配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c337f-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c337f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c337f-112">Remarks</span></span>  
 <span data-ttu-id="c337f-113">`PublicKeyBlob`構造が使用者[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)、 [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)、および他の厳密な名前の関数を公開/秘密キーのペアの公開キーを表します。</span><span class="sxs-lookup"><span data-stu-id="c337f-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c337f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c337f-114">Requirements</span></span>  
 <span data-ttu-id="c337f-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c337f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c337f-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c337f-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c337f-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c337f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c337f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c337f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c337f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c337f-119">See also</span></span>

- [<span data-ttu-id="c337f-120">StrongNameGetPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="c337f-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="c337f-121">StrongNameSignatureGeneration 関数</span><span class="sxs-lookup"><span data-stu-id="c337f-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
