---
title: "ActiveX Control Containers: Manually Enabling ActiveX Control Containment | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-windows"]
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: ["C++"]
helpviewer_keywords: ["AfxEnableControlContainer method [MFC]", "ActiveX control containers [MFC], enabling", "ActiveX controls [MFC], enabling containers"]
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX Control Containers: Manually Enabling ActiveX Control Containment
If you did not enable ActiveX control support when you used the MFC Application Wizard to generate your application, you will have to add this support manually. This article describes the process for manually adding ActiveX control containment to an existing OLE container application. If you know in advance that you want ActiveX control support in your OLE container, see the article [Creating an MFC ActiveX Control Container](../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
> [!NOTE]
>  This article uses a dialog-based ActiveX control container project named Container and an embedded control named Circ as examples in the procedures and code.  
  
 To support ActiveX controls, you must add one line of code to two of your project's files.  
  
-   Modify your main dialog's `InitInstance` function (found in CONTAINER.CPP) by the MFC Application Wizard making a call to [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), as in the following example:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   Add the following to your project's STDAFX.H header file:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 After you have completed these steps, rebuild your project by clicking **Build** on the **Build** menu.  
  
## See Also  
 [ActiveX Control Containers](../mfc/activex-control-containers.md)

