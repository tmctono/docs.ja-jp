---
title: EmitManifest メソッド
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdab1fd10be8fd245f4348798232964721b4487a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777341"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="b6eee-102">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="b6eee-102">EmitManifest Method</span></span>
<span data-ttu-id="b6eee-103">最終的なマニフェストを出力します。</span><span class="sxs-lookup"><span data-stu-id="b6eee-103">Emits the final manifest.</span></span> <span data-ttu-id="b6eee-104">他のすべてのファイルをインポートし、すべてのオプションを設定した後に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6eee-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="b6eee-105">バインドされていないモジュールに対しては、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="b6eee-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6eee-106">構文</span><span class="sxs-lookup"><span data-stu-id="b6eee-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6eee-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6eee-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b6eee-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="b6eee-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="b6eee-109">[StrongNameSignatureSize 関数](../strong-naming/strongnamesignaturesize-function.md)から取得した、アセンブリファイルで予約するサイズを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b6eee-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="b6eee-110">必要に応じて、アセンブリマニフェストトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b6eee-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6eee-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b6eee-111">Return Value</span></span>  
 <span data-ttu-id="b6eee-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b6eee-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6eee-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b6eee-113">Requirements</span></span>  
 <span data-ttu-id="b6eee-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6eee-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6eee-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6eee-115">See also</span></span>

- [<span data-ttu-id="b6eee-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6eee-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b6eee-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6eee-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b6eee-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="b6eee-118">ALink API</span></span>](index.md)
