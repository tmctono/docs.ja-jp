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
ms.openlocfilehash: f3bb978b8358992fd9aa7da922e28efc1ed1a951
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446483"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="39b96-102">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="39b96-102">EmitManifest Method</span></span>
<span data-ttu-id="39b96-103">最終的なマニフェストを出力します。</span><span class="sxs-lookup"><span data-stu-id="39b96-103">Emits the final manifest.</span></span> <span data-ttu-id="39b96-104">他のすべてのファイルをインポートし、すべてのオプションを設定した後に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="39b96-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="39b96-105">バインドされていないモジュールに対しては、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="39b96-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b96-106">構文</span><span class="sxs-lookup"><span data-stu-id="39b96-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b96-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39b96-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="39b96-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="39b96-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="39b96-109">[StrongNameSignatureSize 関数](../strong-naming/strongnamesignaturesize-function.md)から取得した、アセンブリファイルで予約するサイズを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="39b96-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="39b96-110">必要に応じて、アセンブリマニフェストトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="39b96-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39b96-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="39b96-111">Return Value</span></span>  
 <span data-ttu-id="39b96-112">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="39b96-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b96-113">要件</span><span class="sxs-lookup"><span data-stu-id="39b96-113">Requirements</span></span>  
 <span data-ttu-id="39b96-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="39b96-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b96-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="39b96-115">See also</span></span>

- [<span data-ttu-id="39b96-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b96-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="39b96-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b96-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="39b96-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="39b96-118">ALink API</span></span>](index.md)
