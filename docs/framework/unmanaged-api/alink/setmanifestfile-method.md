---
title: SetManifestFile メソッド
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 825bb945e0d8662a4dadc9d688de6a677165df4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741469"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="2cfef-102">SetManifestFile メソッド</span><span class="sxs-lookup"><span data-stu-id="2cfef-102">SetManifestFile Method</span></span>
<span data-ttu-id="2cfef-103">使用すると、指定するか、リンカーがアセンブリを作成するときに使用するマニフェスト ファイルをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="2cfef-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfef-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cfef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cfef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cfef-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="2cfef-106">内容が Win32 リソースの blob に格納するマニフェスト ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2cfef-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cfef-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2cfef-107">Return Value</span></span>  
 <span data-ttu-id="2cfef-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="2cfef-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cfef-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cfef-109">Remarks</span></span>  
 <span data-ttu-id="2cfef-110">これを呼び出して、Win32ResBlob を求めます。</span><span class="sxs-lookup"><span data-stu-id="2cfef-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="2cfef-111">値、`pszFile`パラメーターは、内容の読み取りおよび RT_MANIFEST の ID で Win32 リソースにマニフェスト ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2cfef-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="2cfef-112">NULL のパラメーターを使用して呼び出されると、以前に読み取られた、マニフェストはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="2cfef-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="2cfef-113">これにより、1 つの初期化時に、リンカーの状態をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="2cfef-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfef-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cfef-114">Requirements</span></span>  
 <span data-ttu-id="2cfef-115">ALink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cfef-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfef-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cfef-116">See also</span></span>

- [<span data-ttu-id="2cfef-117">IALink3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cfef-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="2cfef-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="2cfef-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="2cfef-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cfef-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2cfef-120">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="2cfef-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
